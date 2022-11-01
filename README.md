
## VPN service builder library for ARC++
This library exposes the VPN split tunneling apis in ARC.

1. ```
public static void excludeRoute(
      @NonNull Context context, @NonNull VpnService.Builder builder, @NonNull IpPrefix prefix)
      ```

   This api is used to exclude a network route from VPN interface.

2. ```
public static void addRoute(
      @NonNull Context context, @NonNull VpnService.Builder builder, @NonNull IpPrefix prefix)
      ```

   This api is used to add a network route to VPN interface.

#### Steps on how to use the above apis
1. Add vpn_service_builder_client_lib.aar from vpn_service_builder_client_lib_release_package as a dependency in the android project.
2. Import the library

  ```
  import com.google.chromeos.vpn.VpnServiceBuilderCompat;
  ```
3. To use the above apis instantiate VpnService.Builder

    ```
    VpnService mService = new VpnService();
    VpnService.Builder mBuilder = mService.new Builder();
    ```
Configure ```mBuilder``` as you want
4. You can call the above apis in the following way
   * excludeRoute:

    ```
    VpnServiceBuilderCompat.excludeRoute(this, mBuilder, new IpPrefix(inetAddress, prefixLength));
    ```

  * addRoute:

    ```
    VpnServiceBuilderCompat.addRoute(this, mBuilder, new IpPrefix(inetAddress, prefixLength));
    ```
