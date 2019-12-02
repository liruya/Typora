# 获取Home信息问题

Home管理 https://docs.xlink.cn/pages/viewpage.action?pageId=4063395 文档中缺少获取Home信息的接口，因此自己实现了该接口，但使用中出现了如下问题：

在国内可以正常获取Home信息，但在国外或翻墙后获取不到Home信息，提示 error code: 4031003 Access-Token permission invalid  ERROR_API_ACCESS_TOKEN_INVALID

```java
public class Home {
    public int creator;
    public String id;
    public String name;
    public String create_time;
    public int type;
    public List<User> user_list;
    public List<Room> rooms;
    public List<Zone> zones;

    public static class User {
        public int user_id;
        public int role;
        public String email;
        public String nickname;
        public String phone;
        public String avatar;
    }

    public static class Room {
        public String id;
        public String name;
        public List<String> device_ids;
    }

    public static class Zone {
        public String id;
        public String name;
        public List<String> room_ids;
    }
}
```

```java
public interface HomeExtendApi {
    @Headers ({"Content-Type: application/json"})
    @GET ("/v2/home/{home_id}")
    Call<Home> getHomeInfo(@Path("home_id") String homeid, @QueryMap Map<String, Object> var1);
}
```

```java
private final Retrofit mRetrofit = new Retrofit.Builder()
    .baseUrl(XLinkRestful.getBaseRetrofit().baseUrl())                                       	 .client(XLinkRestful.getApiHttpClient().newBuilder().build())
    .addConverterFactory(ScalarsConverterFactory.create())
    .addConverterFactory(GsonConverterFactory.create())
    .build();

public void getHomeInfo(@NonNull final String homeid, final XlinkCallback<Home> callback) {
    Map<String, Object> requestMap = new HashMap<>();
    requestMap.put("user_id", XLinkUserManager.getInstance().getUid());
    HomeExtendApi homeExtendApi = mRetrofit.create(HomeExtendApi.class);
    homeExtendApi.getHomeInfo(homeid, requestMap)
        .enqueue(callback);
}
```

callback返回了上面的error信息