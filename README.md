Small util for GSON serialized configs.


Example usage:

1. Create our Config Class, for example:

```java
(If you use Lombok, there you can just use annotation called @Getter <lombok.Getter> instead of handmade Getters)
public class Config {

    private String hello = "Hello World!";

    public String getHello(){
        return hello;
    }

}
```


2. Create field which will store it


```java
private Config config;

File configFile = new File(plugin.getInstance().getDataFolder(), "exampleConfig.json");
config = (Config) new GsonManager(new Config(), configFile).loadConfigFromObject();

```


3. Now you can use your config.

```java

  System.out.print(config.getHello());

```



