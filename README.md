# AGENCY-WEBHOOK

From 160bf0313c2cb0c55b440678a3b91e8b640ac131 Mon Sep 17 00:00:00 2001
From: keith T bieszczat sr <163609752+grateful345@users.noreply.github.com>
Date: Tue, 19 Mar 2024 19:41:11 -0500
Subject: [PATCH] Update README.md

cr_2coazssVIEva7q1Fw2nwytLIq2N BOT USER bot_2coayXt1oJzWKxgTYyanAjQ3KPV

2dvYx8b2Jxcr6rQ7rMK4g0f5lxd_6MRbqiQJdYkspcWN1vb65 Keith Bieszczat AUTH TOKEN

cr_2dvYx8b2Jxcr6rQ7rMK4g0f5lxd bot_2dvYwRDLFZfzm3QuX1Yfq0xCPZh

2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd API KEY
---
 README.md | 405 ++++++++++++++++++++++++++++++++++++++++++++++++++++++
 1 file changed, 405 insertions(+)

diff --git a/README.md b/README.md
index 7ab556e..71b805e 100644
--- a/README.md
+++ b/README.md
@@ -1,4 +1,409 @@
 # AGENCY-WEBHOOK
+
+
+Repository files navigation
+
+README
+AGENCY-WEBHOOK
+
+API ID KEY SECRET KEY : pst_test_YWNjdF8xTTJKVGtMa2RJd0h1N2l4LE81ZEdIalZ6NlVuMUdjM3c3WkRnN0ZYRHZxRURwTXo_00gNK2DWAV
+
+HystrixCommand command = new HystrixCommand(arg1, arg2);
+
+HystrixObservableCommand command = new HystrixObservableCommand(arg1, arg2);
+
+K value = command.execute(); Future fValue = command.queue(); Observable ohValue = command.observe(); //hot observable Observable ocValue = command.toObservable(); //cold observable Account account = new UserGetAccount(accountId).execute();
+
+//or
+
+Observable accountObservable = new UserGetAccount(accountId).observe();
+
+K value = command.execute(); Future fValue = command.queue(); Observable ohValue = command.observe(); //hot observable Observable ocValue = command.toObservable(); //cold observable
+
+apiVersion: networking.k8s.io/v1 kind: Ingress metadata: name: example-ingress annotations: k8s.ngrok.com/modules: ngrok-module-set spec: ingressClassName: ngrok rules: - host: app.example.com http: paths: - path: / pathType: Prefix backend: service: name: example-service port: number: 80
+
+kind: NgrokModuleSet apiVersion: ingress.k8s.ngrok.com/v1alpha1 metadata: name: ngrok-module-set modules: oauth: google: optionsPassthrough: false inactivityTimeout: 4h maximumDuration: 24h authCheckInterval: 1h apiVersion: networking.k8s.io/v1 kind: Ingress metadata: name: example-ingress annotations: k8s.ngrok.com/modules: ngrok-module-set spec: ingressClassName: ngrok rules: - host: your-domain.ngrok.app http: paths: - path: / pathType: Prefix backend: service: name: example-service port: number: 80
+
+apiVersion: v1 kind: Service metadata: name: example-service annotations: k8s.ngrok.com/app-protocols: '{"example-https-port":"HTTPS"}' spec: ports: - name: example-https-port port: 443 protocol: TCP targetPort: 8443 selector: app-name: some-example-app-label
+
+apiVersion: networking.k8s.io/v1 kind: Ingress metadata: name: example-ingress annotations: k8s.ngrok.com/modules: ngrok-module-set spec: ingressClassName: ngrok rules: - host: app.example.com http: paths: - path: / pathType: Prefix backend: service: name: example-service port: number: 443
+
+kind: NgrokModuleSet apiVersion: ingress.k8s.ngrok.com/v1alpha1 metadata: name: ngrok-module-set modules: headers: request: add: host: "localhost"
+
+apiVersion: networking.k8s.io/v1 kind: Ingress metadata: name: example-ingress annotations: k8s.ngrok.com/modules: ngrok-module-set spec: ingressClassName: ngrok rules: - host: your-domain.ngrok.app http: paths: - path: / pathType: Prefix backend: service: name: example-service port: number: 80
+
+ngrok http 80 --request-header-remove "foo" --request-header-add "foo: new-value" ssh -R 443:localhost:80 v2@connect.ngrok-agent.com http ssh -R example.ngrok.app:443:localhost:80 v2@connect.ngrok-agent.com http ssh -R 443:localhost:80 v2@connect.ngrok-agent.com http
+--basic-auth "username1:password1"
+--basic-auth "username2:password2" ssh -R 443:localhost:80 v2@connect.ngrok-agent.com http --oauth=google ssh -R 0:192.168.1.2:80 v2@connect.ngrok-agent.com http
+
+ssh -R 0:localhost:22 v2@connect.ngrok-agent.com tcp ssh -R 1.tcp.eu.ngrok.io:12345:localhost:3389 connect.eu.ngrok-agent.com tcp ssh -R app.example.com:443:localhost:443 v2@connect.ngrok-agent.com tls ssh -R 443:localhost:80 v2@connect.eu.ngrok-agent.com http
+
+This will cause the HTTP request in this case to become:
+
+GET / HTTP/1.1 host: example.ngrok.app foo: new-value
+
+ngrok http https://httpbin.org --domain your-domain.ngrok.app
+
+In another terminal, curl that endpoint:
+
+curl https://your-domain.ngrok.app/headers
+
+{ "headers": { "Accept": "/", "Accept-Encoding": "gzip", "Host": "your-domain.ngrok.app", "User-Agent": "curl/7.85.0", "X-Amzn-Trace-Id": "Root=1-64d939d7-638343a031ac3f895e36af65" } }
+
+Now, let's try manipulating the headers. We'll remove the user-agent header and add a header of our own with geo data. Stop your previous instance of ngrok with Ctrl+C and then restart ngrok with a new command.
+
+ngrok http https://httpbin.org
+--domain your-domain.ngrok.app
+--request-header-remove='user-agent'
+--request-header-add='country: ${.ngrok.geo.country_code}'
+
+curl https://your-domain.ngrok.app/headers
+
+{ "headers": { "Accept": "/", "Accept-Encoding": "gzip", "Country": "US", "Host": "your-domain.ngrok.app", "X-Amzn-Trace-Id": "Root=1-64d93b73-689c799b056568ff13546ef4" } }
+2coSXkUPJHKNejdfgFKZaF0CjKd_6NvztF58L172P1MHzwAHF NGOK AUTH TOKEN $ ngrok config add-authtoken 2coSXkUPJHKNejdfgFKZaF0CjKd_6NvztF58L172P1MHzwAHF Configuration File Alternatively, you can directly add the Authtoken to your ngrok.yml configuration file. Use ngrok config edit to open the file.
+
+in ngrok.yml
+
+authtoken: 2coSXkUPJHKNejdfgFKZaF0CjKd_6NvztF58L172P1MHzwAHF ep_2dMwdMHSNkmhguqcUSYjAQPryIn ID edge=edghts_2d7h0YrdnMObWZ8UvuA5kKFYMIh rd_2coZL6TjXyPJWuIBdmXP4BVP4Me rd_2coZL6TjXyPJWuIBdmXP4BVP4Me brew install ngrok/ngrok/ngrok
+
+Run the following command to add your authtoken to the default ngrok.yml configuration file.
+
+ngrok config add-authtoken 2coSXkUPJHKNejdfgFKZaF0CjKd_6NvztF58L172P1MHzwAHF
+
+Deploy your app online
+
+Put your app online at ephemeral domain Forwarding to your upstream service. For example, if it is listening on port http://localhost:8080, run:
+
+ngrok http http://localhost:8080 ngrok http --domain=bursting-turkey-really.ngrok-free.app 80 cr_2coSXkUPJHKNejdfgFKZaF0CjKd GOD964v@gmail.com usr_2coSXng7X2Ax9cfBzu5E26b6SDR
+
+cr_2coazssVIEva7q1Fw2nwytLIq2N BOT USER bot_2coayXt1oJzWKxgTYyanAjQ3KPV 
+
+2dvYx8b2Jxcr6rQ7rMK4g0f5lxd_6MRbqiQJdYkspcWN1vb65 Keith Bieszczat AUTH TOKEN 
+
+cr_2dvYx8b2Jxcr6rQ7rMK4g0f5lxd bot_2dvYwRDLFZfzm3QuX1Yfq0xCPZh
+
+2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd API KEY
+
+ngrok config check curl
+-X POST
+-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
+-H "Content-Type: application/json"
+-H "Ngrok-Version: 2"
+-d '{"acl":["bind:1.tcp.ngrok.io:20002","bind:132.devices.company.com"],"description":"for device #132","public_key":"ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDmGS49FkSODAcKhn3+/47DW2zEn19BZvzRQ8RZjL3v6hCIX2qXfsFK35EGxNI0wV23H4xXC2gVRPHKU71YnCb50tad3yMBTM6+2yfGsEDasEH/anmBLclChKvuGiT547RskZlpbAbdq3GvbzmY+R/2EBRMOiObpc8XmSzKAd05j28kqN0+rZO65SWId0MXdvJdSCSAnuRqBNd/aXKlu8hBPDcgwbT2lMkuR+ApoBS2FLRBOiQyt2Ol0T7Uuf7lTLlazpGB3uTw5zFYUNXkuuI6cAP8QYuY1Bne/hNrG8t3Aw9a1yc2C4Fz1hJ/4OMRxTQ8SUQf+Rmxs8DryMlMFJ8r device132@example.com"}'
+https://api.ngrok.com/ssh_credentials { "acl": ["bind:1.tcp.ngrok.io:20002", "bind:132.devices.company.com"], "created_at": "2024-02-16T19:35:31Z", "description": "for device #132", "id": "sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "public_key": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDmGS49FkSODAcKhn3+/47DW2zEn19BZvzRQ8RZjL3v6hCIX2qXfsFK35EGxNI0wV23H4xXC2gVRPHKU71YnCb50tad3yMBTM6+2yfGsEDasEH/anmBLclChKvuGiT547RskZlpbAbdq3GvbzmY+R/2EBRMOiObpc8XmSzKAd05j28kqN0+rZO65SWId0MXdvJdSCSAnuRqBNd/aXKlu8hBPDcgwbT2lMkuR+ApoBS2FLRBOiQyt2Ol0T7Uuf7lTLlazpGB3uTw5zFYUNXkuuI6cAP8QYuY1Bne/hNrG8t3Aw9a1yc2C4Fz1hJ/4OMRxTQ8SUQf+Rmxs8DryMlMFJ8r device132@example.com", "uri": "https://api.ngrok.com/ssh_credentials/sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh" }
+
+curl
+-X GET
+-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
+-H "Ngrok-Version: 2"
+https://api.ngrok.com/ssh_credentials/sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh
+
+{ "acl": ["bind:1.tcp.ngrok.io:20002", "bind:132.devices.company.com"], "created_at": "2024-02-16T19:35:31Z", "description": "my dev machine", "id": "sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh", "metadata": "{"hostname": "macbook.local"}", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "public_key": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDmGS49FkSODAcKhn3+/47DW2zEn19BZvzRQ8RZjL3v6hCIX2qXfsFK35EGxNI0wV23H4xXC2gVRPHKU71YnCb50tad3yMBTM6+2yfGsEDasEH/anmBLclChKvuGiT547RskZlpbAbdq3GvbzmY+R/2EBRMOiObpc8XmSzKAd05j28kqN0+rZO65SWId0MXdvJdSCSAnuRqBNd/aXKlu8hBPDcgwbT2lMkuR+ApoBS2FLRBOiQyt2Ol0T7Uuf7lTLlazpGB3uTw5zFYUNXkuuI6cAP8QYuY1Bne/hNrG8t3Aw9a1yc2C4Fz1hJ/4OMRxTQ8SUQf+Rmxs8DryMlMFJ8r device132@example.com", "uri": "https://api.ngrok.com/ssh_credentials/sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh" }
+
+curl
+-X GET
+-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
+-H "Ngrok-Version: 2"
+https://api.ngrok.com/ssh_credentials
+
+{ "next_page_uri": null, "ssh_credentials": [ { "acl": ["bind:1.tcp.ngrok.io:20002", "bind:132.devices.company.com"], "created_at": "2024-02-16T19:35:31Z", "description": "for device #132", "id": "sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "public_key": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDmGS49FkSODAcKhn3+/47DW2zEn19BZvzRQ8RZjL3v6hCIX2qXfsFK35EGxNI0wV23H4xXC2gVRPHKU71YnCb50tad3yMBTM6+2yfGsEDasEH/anmBLclChKvuGiT547RskZlpbAbdq3GvbzmY+R/2EBRMOiObpc8XmSzKAd05j28kqN0+rZO65SWId0MXdvJdSCSAnuRqBNd/aXKlu8hBPDcgwbT2lMkuR+ApoBS2FLRBOiQyt2Ol0T7Uuf7lTLlazpGB3uTw5zFYUNXkuuI6cAP8QYuY1Bne/hNrG8t3Aw9a1yc2C4Fz1hJ/4OMRxTQ8SUQf+Rmxs8DryMlMFJ8r device132@example.com", "uri": "https://api.ngrok.com/ssh_credentials/sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh" } ], "uri": "https://api.ngrok.com/ssh_credentials" } curl
+-X PATCH
+-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
+-H "Content-Type: application/json"
+-H "Ngrok-Version: 2"
+-d '{"description":"my dev machine","metadata":"{"hostname": "macbook.local"}"}'
+https://api.ngrok.com/ssh_credentials/sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh { "acl": ["bind:1.tcp.ngrok.io:20002", "bind:132.devices.company.com"], "created_at": "2024-02-16T19:35:31Z", "description": "my dev machine", "id": "sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh", "metadata": "{"hostname": "macbook.local"}", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "public_key": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDmGS49FkSODAcKhn3+/47DW2zEn19BZvzRQ8RZjL3v6hCIX2qXfsFK35EGxNI0wV23H4xXC2gVRPHKU71YnCb50tad3yMBTM6+2yfGsEDasEH/anmBLclChKvuGiT547RskZlpbAbdq3GvbzmY+R/2EBRMOiObpc8XmSzKAd05j28kqN0+rZO65SWId0MXdvJdSCSAnuRqBNd/aXKlu8hBPDcgwbT2lMkuR+ApoBS2FLRBOiQyt2Ol0T7Uuf7lTLlazpGB3uTw5zFYUNXkuuI6cAP8QYuY1Bne/hNrG8t3Aw9a1yc2C4Fz1hJ/4OMRxTQ8SUQf+Rmxs8DryMlMFJ8r device132@example.com", "uri": "https://api.ngrok.com/ssh_credentials/sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh" } curl
+-X POST
+-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
+-H "Content-Type: application/json"
+-H "Ngrok-Version: 2"
+-d '{"description":"development cred for alan@example.com"}'
+https://api.ngrok.com/credentials { "acl": [], "created_at": "2024-02-16T19:35:10Z", "description": "development cred for alan@example.com", "id": "cr_2cSjwF80LQJdOIaFZDbLWO9pMxd", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "token": "2cSjwF80LQJdOIaFZDbLWO9pMxd_3qYXgk4mMNpksRrJdRt6Z", "uri": "https://api.ngrok.com/credentials/cr_2cSjwF80LQJdOIaFZDbLWO9pMxd" } curl
+-X GET
+-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
+-H "Ngrok-Version: 2"
+https://api.ngrok.com/credentials/cr_2cSjwF80LQJdOIaFZDbLWO9pMxd
+
+{ "acl": [], "created_at": "2024-02-16T19:35:10Z", "description": "device alpha-2", "id": "cr_2cSjwF80LQJdOIaFZDbLWO9pMxd", "metadata": "{"device_id": "d5111ba7-0cc5-4ba3-8398-e6c79e4e89c2"}", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "token": null, "uri": "https://api.ngrok.com/credentials/cr_2cSjwF80LQJdOIaFZDbLWO9pMxd" } curl
+-X GET
+-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
+-H "Ngrok-Version: 2"
+https://api.ngrok.com/credentials
+
+{ "credentials": [ { "acl": [], "created_at": "2024-02-16T19:35:09Z", "description": "credential for "api-examples-c954256d6ada8b72@example.com"", "id": "cr_2cSjwL9yhXwTeYnIOSxZlvZ8S8y", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "token": null, "uri": "https://api.ngrok.com/credentials/cr_2cSjwL9yhXwTeYnIOSxZlvZ8S8y" }, { "acl": ["bind:1.tcp.ngrok.io:20002", "bind:132.devices.company.com"], "created_at": "2024-02-16T19:35:10Z", "description": "for device #132", "id": "cr_2cSjwHg6uyMl2h31jEgXZOHI77u", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "token": null, "uri": "https://api.ngrok.com/credentials/cr_2cSjwHg6uyMl2h31jEgXZOHI77u" }, { "acl": [], "created_at": "2024-02-16T19:35:10Z", "description": "development cred for alan@example.com", "id": "cr_2cSjwF80LQJdOIaFZDbLWO9pMxd", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "token": null, "uri": "https://api.ngrok.com/credentials/cr_2cSjwF80LQJdOIaFZDbLWO9pMxd" } ], "next_page_uri": null, "uri": "https://api.ngrok.com/credentials" }
+
+curl
+-X PATCH
+-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
+-H "Content-Type: application/json"
+-H "Ngrok-Version: 2"
+-d '{"description":"device alpha-2","metadata":"{"device_id": "d5111ba7-0cc5-4ba3-8398-e6c79e4e89c2"}"}'
+https://api.ngrok.com/credentials/cr_2cSjwF80LQJdOIaFZDbLWO9pMxd { "acl": [], "created_at": "2024-02-16T19:35:10Z", "description": "device alpha-2", "id": "cr_2cSjwF80LQJdOIaFZDbLWO9pMxd", "metadata": "{"device_id": "d5111ba7-0cc5-4ba3-8398-e6c79e4e89c2"}", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "token": null, "uri": "https://api.ngrok.com/credentials/cr_2cSjwF80LQJdOIaFZDbLWO9pMxd" } import ngrok
+
+listener = ngrok.forward("localhost:8080", authtoken_from_env=True, circuit_breaker=0.5)
+
+print(f"Ingress established at: {listener.url()}");
+
+package main
+
+import ( "context" "fmt" "log" "net" "net/http" "net/url" "os"
+
+"golang.ngrok.com/ngrok"
+"golang.ngrok.com/ngrok/config"
+)
+
+func main() { l, err := ngrok.Listen(context.Background(), config.HTTPEndpoint( config.WithCircuitBreaker(0.1), ), ngrok.WithAuthtokenFromEnv(), ) if err != nil { log.Fatal(err) } fmt.Println("Running at", l.URL()) go makeRequests(l.URL()) http.Serve(l, http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) { if r.URL.Path == "/500" { w.WriteHeader(500) fmt.Fprintln(w, "Hello error!") } else { w.WriteHeader(200) fmt.Fprintln(w, "Hello world!") } })) }
+
+func makeRequests(appURL string) { // make sure we always dial the same IP addresss for testing purposes because // circuit breaker state is applied on each ngrok edge server individually u, _ := url.Parse(appURL) addrs, err := net.LookupHost(u.Host) if err != nil { log.Fatal(err) } httpClient := http.Client{Transport: &http.Transport{ Dial: func(network, _ string) (net.Conn, error) { return net.Dial(network, addrs[0]+":443") }, }}
+
+// make requests that return a 500 until the circuit opens
+for {
+	resp, err := httpClient.Get(appURL + "/500")
+	if err != nil {
+		log.Fatal(err)
+	}
+	fmt.Printf("Status Code %d\n", resp.StatusCode)
+	if resp.StatusCode == 503 {
+		fmt.Println("Circuit opened")
+		break
+	}
+}
+
+// make requests that will eventually return a 200 which will close the circuit
+for {
+	resp, err := httpClient.Get(appURL)
+	if err != nil {
+		log.Fatal(err)
+	}
+	fmt.Printf("Status Code %d\n", resp.StatusCode)
+	if resp.StatusCode != 503 {
+		fmt.Println("Circuit closed")
+		os.Exit(0)
+	}
+}
+}
+
+package main
+
+import ( "context" "fmt" "log" "net" "net/http" "net/url" "os"
+
+"golang.ngrok.com/ngrok"
+"golang.ngrok.com/ngrok/config"
+)
+
+func main() { l, err := ngrok.Listen(context.Background(), config.HTTPEndpoint( config.WithCircuitBreaker(0.1), ), ngrok.WithAuthtokenFromEnv(), ) if err != nil { log.Fatal(err) } fmt.Println("Running at", l.URL()) go makeRequests(l.URL()) http.Serve(l, http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) { if r.URL.Path == "/500" { w.WriteHeader(500) fmt.Fprintln(w, "Hello error!") } else { w.WriteHeader(200) fmt.Fprintln(w, "Hello world!") } })) }
+
+func makeRequests(appURL string) { // make sure we always dial the same IP addresss for testing purposes because // circuit breaker state is applied on each ngrok edge server individually u, _ := url.Parse(appURL) addrs, err := net.LookupHost(u.Host) if err != nil { log.Fatal(err) } httpClient := http.Client{Transport: &http.Transport{ Dial: func(network, _ string) (net.Conn, error) { return net.Dial(network, addrs[0]+":443") }, }}
+
+// make requests that return a 500 until the circuit opens
+for {
+	resp, err := httpClient.Get(appURL + "/500")
+	if err != nil {
+		log.Fatal(err)
+	}
+	fmt.Printf("Status Code %d\n", resp.StatusCode)
+	if resp.StatusCode == 503 {
+		fmt.Println("Circuit opened")
+		break
+	}
+}
+
+// make requests that will eventually return a 200 which will close the circuit
+for {
+	resp, err := httpClient.Get(appURL)
+	if err != nil {
+		log.Fatal(err)
+	}
+	fmt.Printf("Status Code %d\n", resp.StatusCode)
+	if resp.StatusCode != 503 {
+		fmt.Println("Circuit closed")
+		os.Exit(0)
+	}
+}
+export NGROK_AUTHTOKEN="<2dvYx8b2Jxcr6rQ7rMK4g0f5lxd_6MRbqiQJdYkspcWN1vb65>" go mod init example.com/ngrok-circuit-breaker go get golang.ngrok.com/ngrok go run example.go import ngrok
+
+listener = ngrok.forward("localhost:8080", authtoken_from_env=True, verify_webhook_provider="twilio", verify_webhook_secret="{twilio signing secret}")
+
+print(f"Ingress established at: {listener.url()}");
+
+git clone https://github.com/ngrok/ngrok-webhook-nodejs-sample.git cd ngrok-webhook-nodejs-sample npm install npm start ngrok http 3000
+
+ngrok http 3000 --verify-webhook stripe --verify-webhook-secret {whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS}
+
+authtoken: 4nq9771bPxe8ctg7LKr_2ClH7Y15Zqe4bWLWF9p api_key: 24yRd5U3DestCQapJrrVHLOqiAC_7RviwRqpd3wc9dKLujQZN connect_timeout: 30s console_ui: true console_ui_color: transparent dns_resolver_ips:
+
+1.1.1.1
+8.8.8.8 heartbeat_interval: 1m heartbeat_tolerance: 5s inspect_db_size: 104857600 # 100mb inspect_db_size: 50000000 log_level: info log_format: json log: /var/log/ngrok.log metadata: '{"serial": "00012xa-33rUtz9", "comment": "For customer alan@example.com"}' proxy_url: socks5://localhost:9150 region: us remote_management: false root_cas: trusted update_channel: stable update_check: false version: 2 web_addr: localhost:4040 tunnels: website: addr: 8888 basic_auth:
+"bob:bobpassword" schemes:
+https host_header: "myapp.ngrok.dev" inspect: false proto: http domain: myapp.ngrok.dev
+e2etls: addr: 9000 proto: tls domain: myapp.example.com crt: example.crt key: example.key
+
+policyenforced: policy: inbound: - name: LimitIPs expressions: - "conn.ClientIP != '1.1.1.1'" actions: - type: deny addr: 8000 proto: tcp
+
+ssh-access: addr: 22 proto: tcp remote_addr: 1.tcp.ngrok.io:12345
+
+my-load-balanced-website: labels: - env=prod - team=infra addr: 8000
+
+tunnels:
+httpbin: proto: http addr: 8000 domain: alan-httpbin.ngrok.dev demo: proto: http addr: 9090 domain: demo.inconshreveable.com inspect: false ngrok start httpbin
+
+tunnels: my-cool-website: labels: - env=prod - team=infra addr: 8000 inspect: false ssh-tunnel: labels: - hostname=my-hostname - service=ssh - team=development addr: 22 api_key: 24yRd5U3DestCQapJrrVHLOqiAC_7RviwRqpd3wc9dKLujQZN authtoken: 4nq9771bPxe8ctg7LKr_2ClH7Y15Zqe4bWLWF9p
+
+log: /var/log/ngrok.log
+
+metadata
+
+This is a user-supplied custom string that will be returned as part of the ngrok API response to the list online sessions resource for all tunnels started by this agent. This is a useful mechanism to identify tunnels by your own device or customer identifier. Maximum 4096 characters.
+
+metadata: bad8c1c0-8fce-11e4-b4a9-0800200c9a66
+
+web_allow_hosts:
+
+8.8.8.8
+example.com curl http://localhost:4040/api/
+{ "tunnels": [ { "name": "command_line", "uri": "/api/tunnels/command_line", "public_url": "https://d95211d2.ngrok.io", "proto": "https", "config": { "addr": "localhost:80", "inspect": true, }, "metrics": { "conns": { "count": 0, "gauge": 0, "rate1": 0, "rate5": 0, "rate15": 0, "p50": 0, "p90": 0, "p95": 0, "p99": 0 }, "http": { "count": 0, "rate1": 0, "rate5": 0, "rate15": 0, "p50": 0, "p90": 0, "p95": 0, "p99": 0 } } }, ... ], "uri": "/api/tunnels" } { "addr": "22", "proto": "tcp", "name": "ssh" }
+
+{ "name": "", "uri": "/api/tunnels/", "public_url": "tcp://0.tcp.ngrok.io:53476", "proto": "tcp", "config": { "addr": "localhost:22", "inspect": false, }, "metrics": { "conns": { "count": 0, "gauge": 0, "rate1": 0, "rate5": 0, "rate15": 0, "p50": 0, "p90": 0, "p95": 0, "p99": 0 }, "http": { "count": 0, "rate1": 0, "rate5": 0, "rate15": 0, "p50": 0, "p90": 0, "p95": 0, "p99": 0 } } }
+
+{ "name": "command_line", "uri": "/api/tunnels/command_line", "public_url": "https://ac294125.ngrok.io", "proto": "https", "config": { "addr": "localhost:80", "inspect": true, }, "metrics": { "conns": { "count": 0, "gauge": 0, "rate1": 0, "rate5": 0, "rate15": 0, "p50": 0, "p90": 0, "p95": 0, "p99": 0 }, "http": { "count": 0, "rate1": 0, "rate5": 0, "rate15": 0, "p50": 0, "p90": 0, "p95": 0, "p99": 0 } } } BHAHZGCJZK3BEVS7IRGZMKDF6USLO runner token apply to all commands
+
+stripe login --api-key sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq
+
+stripe login
+
+stripe trigger payment_intent.succeeded
+
+Secret key
+
+pst_test_YWNjdF8xTTJKVGtMa2RJd0h1N2l4LE81ZEdIalZ6NlVuMUdjM3c3WkRnN0ZYRHZxRURwTXo_00gNK2DWAV run payment id
+
+po_1OZNhvGF83d3fsgWC9jdBgcQ
+
+run bank data DJqIeyHlhjb55r0K Routing number 031101279 ID ba_1OR7BGGF83d3fsgWxwDM4lDf
+
+$ Stripe endpoint we_1Ova66GF83d3fsgW2nbowkDw Webhook signing secret: whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS
+
+why?
+
+req_3SnomkF11VBTwG
+
+The payment failed. { "consent": { "terms_of_service": "accepted" }, "eid": "**", "expected_amount": "100000", "expected_payment_method_type": "link", "guid": "14b84001-905a-42f3-9e2b-18a9ebf0e15c540853", "init_checksum": "MXofbfTYAaKG1no6FZxkzMndcSrERGp3", "js_checksum": "qtod^n0=QU>azbu]Vn<D\^vUO[_esYxY=dwUca$<P<m^o?U^w", "key": "pk_live_*********************************************************************************************k76MVR", "last_displayed_line_item_group_details": { "shipping_rate_amount": "0", "subtotal": "100000", "total_discount_amount": "0", "total_exclusive_tax": "0", "total_inclusive_tax": "0" }, "muid": "eb78b5f0-bdd7-45f9-a924-dcf3e95a1a647d0ae4", "passive_captcha_ekey": "", "passive_captcha_token": "P1_eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJwYXNza2V5IjoibGxxQlR1SURGNkd1WWhCWTh4N1RXY2dLbWJHYUhpdk5DeTZBMDdPTnZ4NUNqdy9XcDkrR0hJTHo0bDdUbHFGSmVjSkNpSFR3N1AyVnZwVHh5RlUyVlgyL0lyZHVCZkc2eTd3RE9tTFRHcUsvUEwxK2V2SWpQcEhwNFRCaVJMaVV2eURPRG4wWnFPa1pONS9NNXVka0dsNER2R3E4djNaMHEvRXRESWZ0ZllNZTBCRVFZTklIU1dROXY3QVRZWHMxWUwvRXhQK3pubmlDUHkvOTQ3Z0kxdjd1Zzk1cG8ycnJGS0ErK2FKeHJsR3lnb3JzRTUwaVNtYm1mNlJuUURPYWcvbWh2OE9GNXg0bE1KMXVNdUw0Rm1UQzNpS2lMell3eDUyNDc2QWlvdEw4aEEzWWVYbEJySkdlT3lxSVRtaytraWY1M05Xd2VjdDY0KytnM3NGL0UrMjg4a04vSUFIQ0FEdEYxbU1vZEFSTjZjL3pvMlBTYUFtdGUzTVV5TTJXT09ZTENWM01VOHRhOHk0emc0d0txSXg0U3lKemxwcCtXVTRvRy9DU0ZRNXYwa29iNVBPMnJtc3QxTkVQT3ozMlNUQ1BFUkZReFdXeWtBaVErc01QbFVmZmhsYnBEcldrMnF6VEQxR0dxQ254MksxeExvYUlhVW5yWWxyNXFZZTVLVHJ4bnNQNUlDVTNrNjBlWVdwbzZBVVJCaGFiOE4rK1g3TEpuRzlLRmJTM2YxM2R5dDM5MlA1WTJZcEFGYUxnT0laSnppSjJOZHkvMXRxbURucFZXaVZrRG1xSjZJRU5UNTh4Y0NvS1oyRjRqVWtGSk5DVWRaejZYdVpLMHY5bGhtRmxoZGRSNGdjVWZQWWFtUjAwUG5wL3c5dXAySkF4UDRRc2RjN2RHUWhCOFJrL0NSVVdFTll5NEFLbXBLeldsMlNscy9SOEpUQUdraGRFdTZvbjNBb2Z5NmZJbC9kK0NCYzlwYjBHeDhaaU9qUmZFbjVMSWNBTUN0Ymp0TFkwaURWWFdQZUM1UUtaMUF1c051TVk2L1lVdFhNZk03eUNyeUVBMG45ajNlYy9hbk9zT01WUWxlWkFDT3RjRmx1KzIvVmlpUDVORG14VGRZc2R4MWU4VFR0MWFpL05IRmxVNXh4cGVmMEFldkx2NXRmWW41WTkxeU1vdGlZaXhvMnhFWkp6NmgycHZRVnpIVnN4aDNNeFRWMWlOZ1kySHVXbVNPbTZjOWdBRWtGZkZCSVM3V2VwY2g2Tng0TzlFVWh0VnpXaW5KRDFvNXZlYkdGMnBJakVYR0lSWVZNSCtWbnJaM2t1V2djOUpiRWtyYStiRjBkd0pxY2F2VityRkdqOW9ENFFSZkMwNmpSMzlvdU5CTmVzSU8xNWRFVE9TdDRHOGxMaUJ4QkhyL283VnR6bHZ2djdhbFI3K3VidlNXdlQ2QlI4cjdOQmxXR3BOM0lCRllnby96a0VJUmRnN0Fzb3RKWndPZENGdnBSbWhDYWJKVklzZTlwSXlrTWl3WGYvUnpTU2wzdkJiMSs4UDBtbFVkNEVCZS9CTnNTcmF4Nm9NWEVmR1c0N29YNFBmMTlqcm9qWnhyaDBOOWJ1b04yWlF0QWQwU255ZndQNUZYYTh2dWp0OGtrUXNlRHZaWVpCRi9TSW1BM2ZRdmM3VnZ5YVNSQktabHBzdFlzMElzYVhpU1pGbFg3NUdrbFVpZWNSREdleFROQVpObWtlN0lTbm4xbVpJaFpUOVlhN1RIdU0yM2dReEs3RnlFcUlzcjNadjYwVDBOSHptdk5lN0w0NkFudDFSbEIxZWQxWW1VN3pvVzdXbGZpOUc0MTZXZ28wQloyUDR6K1hmTXFQc2cwTFdKTytZVFI4Ym0wVzFpQ0ZEdWpUM3l5RGJJN0JWUTlwWDlEMnRjVXE0ajlpSTZjZktrb0d3Z2tCa1dtRmFuQ0QvV3BjTmVnSkJCMEJ0WHR2Z2NSeGQwbmpxR3F2aXIrZGF1TTlNZ0lrZDNLeHNCVXJkd2tySVJhOElvaDlCQmlkUDJMY0pkU1RWUittdFBMRW1iaWZoZVh5clRybUtEcEEvVnNCSmc2MEpBNXp3Q1E5NTlWWWQ5TFh5VnFhdnlrMzRwTC9NaTBPL1dnWmllbUhUNGFVSDdZVG5TekxMYmFQdW1aYVdpMkt4RFFkWmY0cW96akVya21iVnFOSk1XbXYzd2E3QkZhNzdyY0E2RjdXQmRUVkt0V0pqeXp0WWpyTHllNEpST0tsQlh1WmtxbVpnOGNsQlFoNGJobTI4c1FtQzI3UlBkM0dEMGwwTTFyMGpsZitpWDVLc3JGTitHNFJPMzFLT2ZNM2o1ajVzQzBaYytDa2JaNklwK1VKVmk2RmRESUFoMU5LOTl6eWhZR2QwMzlVU2FqdU02TmQxeG4zMTYxVUJQZGpkTFZpb3pFUFZqdXpEZUN6QXNmcDJWUTZyS1JmWUFjNEtVeVdmaEExTThUVHVXL1pJUW5ja2gzUm9UVm5JVE81bkh1YXNGYitYVEJZL0FaOEJzVjRkanFMdUVHc01YQThoV0FYMGxrejJXN1VWZVVINFpHald0T0d0SHZBZURJOTJiT0V4OXk0YWhrWU93czYyWURHL1F5c1FNc2pFWFMzb3d4ekcvNVBZaVJ6RlAwaDFYS09McXhNdmYrM2NlYlN3UkNOdkhMV2tYT2k1bk82TzROait5OGR2UGhVSWVBS0tWTTBGTmw5UW1XNzBFTEdPZjVOZzdWZGRBY3RWd3VsOUo0elAyUGhsOFF5bi8xK1l2bFpXMmpHUmQ3eXd2cUZVVVlPU2htNkk2VFB2eG4vVCtKWHJ4WUlaMmVnbVoyVy91UEhXbVFucGtZUUYzaEhIYnlkbnhDOEpGa2E3NGJNQjZRR3J0VHBvaGhUOFo1U0lXU1Iwbkt3UHhBOGdZaThDRlhKRXErcFpkT1RNYUhiay9RcDJmMFFCQXA4aEpKMU5IUWdrRCtZdEFBTnV5bWR5YW90RmJQeS9STnJyS1AyOTZiUlF5SVV4aU10dlo2Z1piMFRqK252WTRUVFU4UzNNWW14Nysrd242N1Rxcm11Zytjc3FMNEJVdnhmdGlCWnI3b0M1cnNmRFQ5d21XSS8iLCJleHAiOjE3MTA3NDI1OTksInNoYXJkX2lkIjo4MzM0NDA4OTcsInBkIjowLCJjZGF0YSI6IjRKOGNUeDBPRjd6byszdzB1WHNtZ0dzSEpubE5Geml0VUZON0dhYWNzQWpFdWZsbmlta3lydXpwT2FGVnl5S2hXSk9tVmdwcEdtOFZtMWNWOWJnL3BacDhHcDVmN1N0ZEpvTlU5M0JhaHRKbmE4V2pNZkVEWnp0QUUwTXRMQ0Qxb1Z2dzc4SDlJREdqK0FmTXVaZFp0OFpiT0JmZ1dmZUluRVVLNUx0dHhnOGtaUU93dW91S0ExTmxRamxiQk9vM1NGT1ZFdERPdTlESjdsN2JZL0x0OU9KME9NNTBZTjQ9VkpFeHI4ZHFFQWpuenI1UiJ9.pPcNQ2Y328R8U7Sar4Z5U0GO9y1caCAAPmbIy3aCnYo", "payment_method": "pm_1OvZUOGF83d3fsgWiXYpUHQh", "rv_timestamp": "qto>n<Q=U&CyY&>X^r<YNr<YN<Y_C<Y_C<Y^zY_<Y^n{U>o&U&CyY=P=eODdbL%e&areOMrY=n=YxnDd_Mv[bL>[OTCdOaveu%euUyX%n{U>e&U&Cyd&auY_n=d&;;X_d%d&UxdRP#[bd#exQxX=L&X&n%eu\\$ex]sY&ovXOUu[_$reunDd&osd=MueOP;d&<yY_<sX^o?U^w", "sid": "f931f0fd-f83a-4921-903f-45f5b359d9925f3b2a", "version": "2d3a08de7b" }
+
+pip3 install stripe python3 -m flask run --port=4242 python3 -m flask run --port=4242 $ stripe listen --forward-to localhost:4242/webhook $ stripe trigger payment_intent.succeeded #! /usr/bin/env python3.6
+
+Python 3.6 or newer required.
+
+import json import os import stripe
+
+This is your test secret API key.
+
+stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'
+
+#! /usr/bin/env python3.6
+
+Python 3.6 or newer required.
+
+import json import os import stripe
+
+This is your test secret API key.
+
+stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'
+
+Replace this endpoint secret with your endpoint's unique secret
+
+If you are testing with the CLI, find the secret by running 'stripe listen'
+
+If you are using an endpoint defined with the API or dashboard, look in your webhook settings
+
+at https://dashboard.stripe.com/webhooks
+
+endpoint_secret = 'whsec_...' from flask import Flask, jsonify, request
+
+app = Flask(name)
+
+@app.route('/webhook', methods=['POST']) def webhook(): event = None payload = request.data
+
+try:
+    event = json.loads(payload)
+except json.decoder.JSONDecodeError as e:
+    print('⚠️  Webhook error while parsing basic request.' + str(e))
+    return jsonify(success=False)
+if endpoint_secret:
+    # Only verify the event if there is an endpoint secret defined
+    # Otherwise use the basic event deserialized with json
+    sig_header = request.headers.get('stripe-signature')
+    try:
+        event = stripe.Webhook.construct_event(
+            payload, sig_header, endpoint_secret
+        )
+    except stripe.error.SignatureVerificationError as e:
+        print('⚠️  Webhook signature verification failed.' + str(e))
+        return jsonify(success=False)
+
+# Handle the event
+if event and event['type'] == 'payment_intent.succeeded':
+    payment_intent = event['data']['object']  # contains a stripe.PaymentIntent
+    print('Payment for {} succeeded'.format(payment_intent['amount']))
+    # Then define and call a method to handle the successful payment intent.
+    # handle_payment_intent_succeeded(payment_intent)
+elif event['type'] == 'payment_method.attached':
+    payment_method = event['data']['object']  # contains a stripe.PaymentMethod
+    # Then define and call a method to handle the successful attachment of a PaymentMethod.
+    # handle_payment_method_attached(payment_method)
+else:
+    # Unexpected event type
+    print('Unhandled event type {}'.format(event['type']))
+
+return jsonify(success=True)
+Run
+
+https://dashboard.stripe.com/test/payouts/po_1OZNhvGF83d3fsgWC9jdBgcQ#wb-N4Igdghgbglg5hALjA9mEAuUEDGyoCmAKhAEaYgAmBAzspMmjSADQiJkASMdKATgE9MAbQC6bPigCuiAt16CRogL5saMAF4wwcTGCkAbA2wAWBeCcQUA7AAYoJ1iFjrSMAzEQCAsimoUXGFIDAidqOm0kVDBmLBAaAhC8AkoASUoKAHcCAH0ARgB5KAgANhKAcQAxAA4AZkpagDMaOAB1ACYwUhRMgGsAEUynDnIMEAJCMERmNgmCKdjQRvdZPkX4ggg+HEcxpzokKVixCVppbdC9thRSACsCPHSKJzmpogEAB0uQF75JPneXyUbEoSEuwGUqg2SVkaQyGH0RjUiQesIAgohZABbD6IJ4IwwGSHKIA
+
+Download Stripe client secret
+
+const {client_secret: seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ/ } = await res.json();
+
+const {error} = await stripe.confirmPayment({ //Elements instance that was used to create the Payment Element elements, clientSecret, confirmParams: { return_url: 'https://example.com/order/123/complete', }, });
+
+if (error) { // This point will only be reached if there is an immediate error when // confirming the payment. Show error to your customer (for example, payment // details incomplete) setErrorMessage(error.message); } else { // Your customer will be redirected to your return_url. For some payment // methods like iDEAL, your customer will be redirected to an intermediate // site first to authorize the payment, then redirected to the return_url. } import stripe stripe.api_key = "sk_test_51OR5eP...OF00CdDfT6Xqsk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq" stripe.Event.list(limit=3) RESPONSE { "object": "list", "url": "/v1/events", "has_more": false, "data": [ { "id": "evt_1NG8Du2eZvKYlo2CUI79vXWy", "object": "event", "api_version": "2019-02-19", "created": 1686089970, "data": { "object": { "id": "seti_1NG8Du2eZvKYlo2C9XMqbR0x", "object": "setup_intent", "application": null, "automatic_payment_methods": null, "cancellation_reason": null, "client_secret": "seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ", "created": 1686089970, "customer": null, "description": null, "flow_directions": null, "last_setup_error": null, "latest_attempt": null, "livemode": false, "mandate": null, "metadata": {}, "next_action": null, "on_behalf_of": null, "payment_method": "pm_1NG8Du2eZvKYlo2CYzzldNr7", "payment_method_options": { "acss_debit": { "currency": "cad", "mandate_options": { "interval_description": "First day of every month", "payment_schedule": "interval", "transaction_type": "personal" }, "verification_method": "automatic" } }, "payment_method_types": [ "acss_debit" ], "single_use_mandate": null, "status": "requires_confirmation", "usage": "off_session" } }, "livemode": false, "pending_webhooks": 0, "request": { "id": null, "idempotency_key": null }, "type": "setup_intent.created" } {...} {...} ], }
+
+OK ID req_ZIIVfKfNp6QrOh
+
+const {client_secret: seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ} = await res.json();
+
+const {error} = await stripe.confirmPayment({ //Elements instance that was used to create the Payment Element elements, clientSecret, confirmParams: { return_url: 'https://example.com/order/123/complete', }, });
+
+if (error) { // This point will only be reached if there is an immediate error when // confirming the payment. Show error to your customer (for example, payment // details incomplete) setErrorMessage(error.message); } else { // Your customer will be redirected to your return_url. For some payment // methods like iDEAL, your customer will be redirected to an intermediate // site first to authorize the payment, then redirected to the return_url. } import stripe stripe.api_key = "sk_test_51OR5eP...OF00CdDfT6Xqsk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq" stripe.Event.list(limit=3) RESPONSE { "object": "list", "url": "/v1/events", "has_more": false, "data": [ { "id": "evt_1NG8Du2eZvKYlo2CUI79vXWy", "object": "event", "api_version": "2019-02-19", "created": 1686089970, "data": { "object": { "id": "seti_1NG8Du2eZvKYlo2C9XMqbR0x", "object": "setup_intent", "application": null, "automatic_payment_methods": null, "cancellation_reason": null, "client_secret": "seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ", "created": 1686089970, "customer": null, "description": null, "flow_directions": null, "last_setup_error": null, "latest_attempt": null, "livemode": false, "mandate": null, "metadata": {}, "next_action": null, "on_behalf_of": null, "payment_method": "pm_1NG8Du2eZvKYlo2CYzzldNr7", "payment_method_options": { "acss_debit": { "currency": "cad", "mandate_options": { "interval_description": "First day of every month", "payment_schedule": "interval", "transaction_type": "personal" }, "verification_method": "automatic" } }, "payment_method_types": [ "acss_debit" ], "single_use_mandate": null, "status": "requires_confirmation", "usage": "off_session" } }, "livemode": false, "pending_webhooks": 0, "request": { "id": null, "idempotency_key": 6f5410cb-1ecc-4302-8130-baf8dd8c0a50 }, "type": "setup_intent.created" } {...} {...} ], }
+
+stripe .retrieveSetupIntent( '{fcsess_client_secret_KRJTKvCY3IKoYTrW18EazcO3 /seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ }', ) .then(function(result) { // Handle result.error or result.paymentIntent }); stripe.collectFinancialConnectionsAccounts({ clientSecret: '{fcsess_client_secret_KRJTKvCY3IKoYTrW18EazcO3}' }) .then(function(result) { if (result.error) { // Inform the customer that there was an error. console.log(result.error.message);
+
+// Handle next step based on length of accounts array
+} else if (result.financialConnectionsSession.accounts.length === 0) {
+  console.log('No accounts were linked');
+} else {
+  console.log(result.financialConnectionsSession.accounts)
+}
+});
+
+{ "object": "customer_session", "client_secret": "_POpxYpmkXdtttYtZQYhrsOJZ2RCQ9kCqqXRU6qrP5c4Jgje", "components": { "buy_button": { "enabled": false }, "pricing_table": { "enabled": true } }, "customer": "cus_PO34b57IOUb83c", "expires_at": 1684790027, "livemode": false } { "object": "customer_session", "client_secret": "_POpxYpmkXdtttYtZQYhrsOJZ2RCQ9kCqqXRU6qrP5c4Jgje", "components": { "buy_button": { "enabled": false }, "pricing_table": { "enabled": true } }, "customer": "cus_PO34b57IOUb83c", "expires_at": 1684790027, "livemode": false }
+
+Create a folder $ mkdir actions-runner && cd actions-runner
+
+Download the latest runner package $ curl -o actions-runner-osx-x64-2.314.1.tar.gz -L https://github.com/actions/runner/releases/download/v2.314.1/actions-runner-osx-x64-2.314.1.tar.gz
+
+Optional: Validate the hash $ echo "3faff4667d6d12c41da962580168415d628e3ffba9924b9ac995752087efc921 actions-runner-osx-x64-2.314.1.tar.gz" | shasum -a 256 -c
+
+Extract the installer $ tar xzf ./actions-runner-osx-x64-2.314.1.tar.gz Configure
+
+Create the runner and start the configuration experience $ ./config.sh --url https://github.com/grateful345/Wiz-Go-call-sign --token BHAHZGDHHICG3LFF53OICRLF6UR24
+
+Last step, run it! $ ./run.sh Using your self-hosted runner
+
+Use this YAML in your workflow file for each job runs-on: self-hosted
+
+Orginization ID: e3ff35d1-cea4-4508-acb5-99d9cbd91e80
+
+
 pk_live_51OR5ePGF83d3fsgW22PwNtYiShCVYIsrzZq2WxlxN2UAaB2qEIu0aUFJzjJxPtNT3rAs0Rvdo9XIVPb7rRMaeo3W00ALk76MVR PUBLISHABLE KEY LIVE
 
 sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq secret test key STRIPERepository files navigation

README
AGENCY-WEBHOOK

API ID KEY SECRET KEY : pst_test_YWNjdF8xTTJKVGtMa2RJd0h1N2l4LE81ZEdIalZ6NlVuMUdjM3c3WkRnN0ZYRHZxRURwTXo_00gNK2DWAV

HystrixCommand command = new HystrixCommand(arg1, arg2);

HystrixObservableCommand command = new HystrixObservableCommand(arg1, arg2);

K value = command.execute(); Future fValue = command.queue(); Observable ohValue = command.observe(); //hot observable Observable ocValue = command.toObservable(); //cold observable Account account = new UserGetAccount(accountId).execute();

//or

Observable accountObservable = new UserGetAccount(accountId).observe();

K value = command.execute(); Future fValue = command.queue(); Observable ohValue = command.observe(); //hot observable Observable ocValue = command.toObservable(); //cold observable

apiVersion: networking.k8s.io/v1 kind: Ingress metadata: name: example-ingress annotations: k8s.ngrok.com/modules: ngrok-module-set spec: ingressClassName: ngrok rules: - host: app.example.com http: paths: - path: / pathType: Prefix backend: service: name: example-service port: number: 80

kind: NgrokModuleSet apiVersion: ingress.k8s.ngrok.com/v1alpha1 metadata: name: ngrok-module-set modules: oauth: google: optionsPassthrough: false inactivityTimeout: 4h maximumDuration: 24h authCheckInterval: 1h apiVersion: networking.k8s.io/v1 kind: Ingress metadata: name: example-ingress annotations: k8s.ngrok.com/modules: ngrok-module-set spec: ingressClassName: ngrok rules: - host: your-domain.ngrok.app http: paths: - path: / pathType: Prefix backend: service: name: example-service port: number: 80

apiVersion: v1 kind: Service metadata: name: example-service annotations: k8s.ngrok.com/app-protocols: '{"example-https-port":"HTTPS"}' spec: ports: - name: example-https-port port: 443 protocol: TCP targetPort: 8443 selector: app-name: some-example-app-label

apiVersion: networking.k8s.io/v1 kind: Ingress metadata: name: example-ingress annotations: k8s.ngrok.com/modules: ngrok-module-set spec: ingressClassName: ngrok rules: - host: app.example.com http: paths: - path: / pathType: Prefix backend: service: name: example-service port: number: 443

kind: NgrokModuleSet apiVersion: ingress.k8s.ngrok.com/v1alpha1 metadata: name: ngrok-module-set modules: headers: request: add: host: "localhost"

apiVersion: networking.k8s.io/v1 kind: Ingress metadata: name: example-ingress annotations: k8s.ngrok.com/modules: ngrok-module-set spec: ingressClassName: ngrok rules: - host: your-domain.ngrok.app http: paths: - path: / pathType: Prefix backend: service: name: example-service port: number: 80

ngrok http 80 --request-header-remove "foo" --request-header-add "foo: new-value" ssh -R 443:localhost:80 v2@connect.ngrok-agent.com http ssh -R example.ngrok.app:443:localhost:80 v2@connect.ngrok-agent.com http ssh -R 443:localhost:80 v2@connect.ngrok-agent.com http
--basic-auth "username1:password1"
--basic-auth "username2:password2" ssh -R 443:localhost:80 v2@connect.ngrok-agent.com http --oauth=google ssh -R 0:192.168.1.2:80 v2@connect.ngrok-agent.com http

ssh -R 0:localhost:22 v2@connect.ngrok-agent.com tcp ssh -R 1.tcp.eu.ngrok.io:12345:localhost:3389 connect.eu.ngrok-agent.com tcp ssh -R app.example.com:443:localhost:443 v2@connect.ngrok-agent.com tls ssh -R 443:localhost:80 v2@connect.eu.ngrok-agent.com http

This will cause the HTTP request in this case to become:

GET / HTTP/1.1 host: example.ngrok.app foo: new-value

ngrok http https://httpbin.org --domain your-domain.ngrok.app

In another terminal, curl that endpoint:

curl https://your-domain.ngrok.app/headers

{ "headers": { "Accept": "/", "Accept-Encoding": "gzip", "Host": "your-domain.ngrok.app", "User-Agent": "curl/7.85.0", "X-Amzn-Trace-Id": "Root=1-64d939d7-638343a031ac3f895e36af65" } }

Now, let's try manipulating the headers. We'll remove the user-agent header and add a header of our own with geo data. Stop your previous instance of ngrok with Ctrl+C and then restart ngrok with a new command.

ngrok http https://httpbin.org
--domain your-domain.ngrok.app
--request-header-remove='user-agent'
--request-header-add='country: ${.ngrok.geo.country_code}'

curl https://your-domain.ngrok.app/headers

{ "headers": { "Accept": "/", "Accept-Encoding": "gzip", "Country": "US", "Host": "your-domain.ngrok.app", "X-Amzn-Trace-Id": "Root=1-64d93b73-689c799b056568ff13546ef4" } }
2coSXkUPJHKNejdfgFKZaF0CjKd_6NvztF58L172P1MHzwAHF NGOK AUTH TOKEN $ ngrok config add-authtoken 2coSXkUPJHKNejdfgFKZaF0CjKd_6NvztF58L172P1MHzwAHF Configuration File Alternatively, you can directly add the Authtoken to your ngrok.yml configuration file. Use ngrok config edit to open the file.

in ngrok.yml

authtoken: 2coSXkUPJHKNejdfgFKZaF0CjKd_6NvztF58L172P1MHzwAHF ep_2dMwdMHSNkmhguqcUSYjAQPryIn ID edge=edghts_2d7h0YrdnMObWZ8UvuA5kKFYMIh rd_2coZL6TjXyPJWuIBdmXP4BVP4Me rd_2coZL6TjXyPJWuIBdmXP4BVP4Me brew install ngrok/ngrok/ngrok

Run the following command to add your authtoken to the default ngrok.yml configuration file.

ngrok config add-authtoken 2coSXkUPJHKNejdfgFKZaF0CjKd_6NvztF58L172P1MHzwAHF

Deploy your app online

Put your app online at ephemeral domain Forwarding to your upstream service. For example, if it is listening on port http://localhost:8080, run:

ngrok http http://localhost:8080 ngrok http --domain=bursting-turkey-really.ngrok-free.app 80 cr_2coSXkUPJHKNejdfgFKZaF0CjKd GOD964v@gmail.com usr_2coSXng7X2Ax9cfBzu5E26b6SDR

cr_2coazssVIEva7q1Fw2nwytLIq2N BOT USER bot_2coayXt1oJzWKxgTYyanAjQ3KPV 

2dvYx8b2Jxcr6rQ7rMK4g0f5lxd_6MRbqiQJdYkspcWN1vb65 Keith Bieszczat AUTH TOKEN 

cr_2dvYx8b2Jxcr6rQ7rMK4g0f5lxd bot_2dvYwRDLFZfzm3QuX1Yfq0xCPZh

2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd API KEY

ngrok config check curl
-X POST
-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
-H "Content-Type: application/json"
-H "Ngrok-Version: 2"
-d '{"acl":["bind:1.tcp.ngrok.io:20002","bind:132.devices.company.com"],"description":"for device #132","public_key":"ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDmGS49FkSODAcKhn3+/47DW2zEn19BZvzRQ8RZjL3v6hCIX2qXfsFK35EGxNI0wV23H4xXC2gVRPHKU71YnCb50tad3yMBTM6+2yfGsEDasEH/anmBLclChKvuGiT547RskZlpbAbdq3GvbzmY+R/2EBRMOiObpc8XmSzKAd05j28kqN0+rZO65SWId0MXdvJdSCSAnuRqBNd/aXKlu8hBPDcgwbT2lMkuR+ApoBS2FLRBOiQyt2Ol0T7Uuf7lTLlazpGB3uTw5zFYUNXkuuI6cAP8QYuY1Bne/hNrG8t3Aw9a1yc2C4Fz1hJ/4OMRxTQ8SUQf+Rmxs8DryMlMFJ8r device132@example.com"}'
https://api.ngrok.com/ssh_credentials { "acl": ["bind:1.tcp.ngrok.io:20002", "bind:132.devices.company.com"], "created_at": "2024-02-16T19:35:31Z", "description": "for device #132", "id": "sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "public_key": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDmGS49FkSODAcKhn3+/47DW2zEn19BZvzRQ8RZjL3v6hCIX2qXfsFK35EGxNI0wV23H4xXC2gVRPHKU71YnCb50tad3yMBTM6+2yfGsEDasEH/anmBLclChKvuGiT547RskZlpbAbdq3GvbzmY+R/2EBRMOiObpc8XmSzKAd05j28kqN0+rZO65SWId0MXdvJdSCSAnuRqBNd/aXKlu8hBPDcgwbT2lMkuR+ApoBS2FLRBOiQyt2Ol0T7Uuf7lTLlazpGB3uTw5zFYUNXkuuI6cAP8QYuY1Bne/hNrG8t3Aw9a1yc2C4Fz1hJ/4OMRxTQ8SUQf+Rmxs8DryMlMFJ8r device132@example.com", "uri": "https://api.ngrok.com/ssh_credentials/sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh" }

curl
-X GET
-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
-H "Ngrok-Version: 2"
https://api.ngrok.com/ssh_credentials/sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh

{ "acl": ["bind:1.tcp.ngrok.io:20002", "bind:132.devices.company.com"], "created_at": "2024-02-16T19:35:31Z", "description": "my dev machine", "id": "sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh", "metadata": "{"hostname": "macbook.local"}", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "public_key": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDmGS49FkSODAcKhn3+/47DW2zEn19BZvzRQ8RZjL3v6hCIX2qXfsFK35EGxNI0wV23H4xXC2gVRPHKU71YnCb50tad3yMBTM6+2yfGsEDasEH/anmBLclChKvuGiT547RskZlpbAbdq3GvbzmY+R/2EBRMOiObpc8XmSzKAd05j28kqN0+rZO65SWId0MXdvJdSCSAnuRqBNd/aXKlu8hBPDcgwbT2lMkuR+ApoBS2FLRBOiQyt2Ol0T7Uuf7lTLlazpGB3uTw5zFYUNXkuuI6cAP8QYuY1Bne/hNrG8t3Aw9a1yc2C4Fz1hJ/4OMRxTQ8SUQf+Rmxs8DryMlMFJ8r device132@example.com", "uri": "https://api.ngrok.com/ssh_credentials/sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh" }

curl
-X GET
-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
-H "Ngrok-Version: 2"
https://api.ngrok.com/ssh_credentials

{ "next_page_uri": null, "ssh_credentials": [ { "acl": ["bind:1.tcp.ngrok.io:20002", "bind:132.devices.company.com"], "created_at": "2024-02-16T19:35:31Z", "description": "for device #132", "id": "sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "public_key": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDmGS49FkSODAcKhn3+/47DW2zEn19BZvzRQ8RZjL3v6hCIX2qXfsFK35EGxNI0wV23H4xXC2gVRPHKU71YnCb50tad3yMBTM6+2yfGsEDasEH/anmBLclChKvuGiT547RskZlpbAbdq3GvbzmY+R/2EBRMOiObpc8XmSzKAd05j28kqN0+rZO65SWId0MXdvJdSCSAnuRqBNd/aXKlu8hBPDcgwbT2lMkuR+ApoBS2FLRBOiQyt2Ol0T7Uuf7lTLlazpGB3uTw5zFYUNXkuuI6cAP8QYuY1Bne/hNrG8t3Aw9a1yc2C4Fz1hJ/4OMRxTQ8SUQf+Rmxs8DryMlMFJ8r device132@example.com", "uri": "https://api.ngrok.com/ssh_credentials/sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh" } ], "uri": "https://api.ngrok.com/ssh_credentials" } curl
-X PATCH
-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
-H "Content-Type: application/json"
-H "Ngrok-Version: 2"
-d '{"description":"my dev machine","metadata":"{"hostname": "macbook.local"}"}'
https://api.ngrok.com/ssh_credentials/sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh { "acl": ["bind:1.tcp.ngrok.io:20002", "bind:132.devices.company.com"], "created_at": "2024-02-16T19:35:31Z", "description": "my dev machine", "id": "sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh", "metadata": "{"hostname": "macbook.local"}", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "public_key": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDmGS49FkSODAcKhn3+/47DW2zEn19BZvzRQ8RZjL3v6hCIX2qXfsFK35EGxNI0wV23H4xXC2gVRPHKU71YnCb50tad3yMBTM6+2yfGsEDasEH/anmBLclChKvuGiT547RskZlpbAbdq3GvbzmY+R/2EBRMOiObpc8XmSzKAd05j28kqN0+rZO65SWId0MXdvJdSCSAnuRqBNd/aXKlu8hBPDcgwbT2lMkuR+ApoBS2FLRBOiQyt2Ol0T7Uuf7lTLlazpGB3uTw5zFYUNXkuuI6cAP8QYuY1Bne/hNrG8t3Aw9a1yc2C4Fz1hJ/4OMRxTQ8SUQf+Rmxs8DryMlMFJ8r device132@example.com", "uri": "https://api.ngrok.com/ssh_credentials/sshcr_2cSjyydertQFE3OLV3NIEJIp6Kh" } curl
-X POST
-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
-H "Content-Type: application/json"
-H "Ngrok-Version: 2"
-d '{"description":"development cred for alan@example.com"}'
https://api.ngrok.com/credentials { "acl": [], "created_at": "2024-02-16T19:35:10Z", "description": "development cred for alan@example.com", "id": "cr_2cSjwF80LQJdOIaFZDbLWO9pMxd", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "token": "2cSjwF80LQJdOIaFZDbLWO9pMxd_3qYXgk4mMNpksRrJdRt6Z", "uri": "https://api.ngrok.com/credentials/cr_2cSjwF80LQJdOIaFZDbLWO9pMxd" } curl
-X GET
-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
-H "Ngrok-Version: 2"
https://api.ngrok.com/credentials/cr_2cSjwF80LQJdOIaFZDbLWO9pMxd

{ "acl": [], "created_at": "2024-02-16T19:35:10Z", "description": "device alpha-2", "id": "cr_2cSjwF80LQJdOIaFZDbLWO9pMxd", "metadata": "{"device_id": "d5111ba7-0cc5-4ba3-8398-e6c79e4e89c2"}", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "token": null, "uri": "https://api.ngrok.com/credentials/cr_2cSjwF80LQJdOIaFZDbLWO9pMxd" } curl
-X GET
-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
-H "Ngrok-Version: 2"
https://api.ngrok.com/credentials

{ "credentials": [ { "acl": [], "created_at": "2024-02-16T19:35:09Z", "description": "credential for "api-examples-c954256d6ada8b72@example.com"", "id": "cr_2cSjwL9yhXwTeYnIOSxZlvZ8S8y", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "token": null, "uri": "https://api.ngrok.com/credentials/cr_2cSjwL9yhXwTeYnIOSxZlvZ8S8y" }, { "acl": ["bind:1.tcp.ngrok.io:20002", "bind:132.devices.company.com"], "created_at": "2024-02-16T19:35:10Z", "description": "for device #132", "id": "cr_2cSjwHg6uyMl2h31jEgXZOHI77u", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "token": null, "uri": "https://api.ngrok.com/credentials/cr_2cSjwHg6uyMl2h31jEgXZOHI77u" }, { "acl": [], "created_at": "2024-02-16T19:35:10Z", "description": "development cred for alan@example.com", "id": "cr_2cSjwF80LQJdOIaFZDbLWO9pMxd", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "token": null, "uri": "https://api.ngrok.com/credentials/cr_2cSjwF80LQJdOIaFZDbLWO9pMxd" } ], "next_page_uri": null, "uri": "https://api.ngrok.com/credentials" }

curl
-X PATCH
-H "Authorization: Bearer {2dvZEkjdgaLw0K0a5G0RX80fTjJ_k2h32aY22XRhNpU5qeWd}"
-H "Content-Type: application/json"
-H "Ngrok-Version: 2"
-d '{"description":"device alpha-2","metadata":"{"device_id": "d5111ba7-0cc5-4ba3-8398-e6c79e4e89c2"}"}'
https://api.ngrok.com/credentials/cr_2cSjwF80LQJdOIaFZDbLWO9pMxd { "acl": [], "created_at": "2024-02-16T19:35:10Z", "description": "device alpha-2", "id": "cr_2cSjwF80LQJdOIaFZDbLWO9pMxd", "metadata": "{"device_id": "d5111ba7-0cc5-4ba3-8398-e6c79e4e89c2"}", "owner_id": "usr_2cSjwF6w6AynjfPtm4Ww5xTdkId", "token": null, "uri": "https://api.ngrok.com/credentials/cr_2cSjwF80LQJdOIaFZDbLWO9pMxd" } import ngrok

listener = ngrok.forward("localhost:8080", authtoken_from_env=True, circuit_breaker=0.5)

print(f"Ingress established at: {listener.url()}");

package main

import ( "context" "fmt" "log" "net" "net/http" "net/url" "os"

"golang.ngrok.com/ngrok"
"golang.ngrok.com/ngrok/config"
)

func main() { l, err := ngrok.Listen(context.Background(), config.HTTPEndpoint( config.WithCircuitBreaker(0.1), ), ngrok.WithAuthtokenFromEnv(), ) if err != nil { log.Fatal(err) } fmt.Println("Running at", l.URL()) go makeRequests(l.URL()) http.Serve(l, http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) { if r.URL.Path == "/500" { w.WriteHeader(500) fmt.Fprintln(w, "Hello error!") } else { w.WriteHeader(200) fmt.Fprintln(w, "Hello world!") } })) }

func makeRequests(appURL string) { // make sure we always dial the same IP addresss for testing purposes because // circuit breaker state is applied on each ngrok edge server individually u, _ := url.Parse(appURL) addrs, err := net.LookupHost(u.Host) if err != nil { log.Fatal(err) } httpClient := http.Client{Transport: &http.Transport{ Dial: func(network, _ string) (net.Conn, error) { return net.Dial(network, addrs[0]+":443") }, }}

// make requests that return a 500 until the circuit opens
for {
	resp, err := httpClient.Get(appURL + "/500")
	if err != nil {
		log.Fatal(err)
	}
	fmt.Printf("Status Code %d\n", resp.StatusCode)
	if resp.StatusCode == 503 {
		fmt.Println("Circuit opened")
		break
	}
}

// make requests that will eventually return a 200 which will close the circuit
for {
	resp, err := httpClient.Get(appURL)
	if err != nil {
		log.Fatal(err)
	}
	fmt.Printf("Status Code %d\n", resp.StatusCode)
	if resp.StatusCode != 503 {
		fmt.Println("Circuit closed")
		os.Exit(0)
	}
}
}

package main

import ( "context" "fmt" "log" "net" "net/http" "net/url" "os"

"golang.ngrok.com/ngrok"
"golang.ngrok.com/ngrok/config"
)

func main() { l, err := ngrok.Listen(context.Background(), config.HTTPEndpoint( config.WithCircuitBreaker(0.1), ), ngrok.WithAuthtokenFromEnv(), ) if err != nil { log.Fatal(err) } fmt.Println("Running at", l.URL()) go makeRequests(l.URL()) http.Serve(l, http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) { if r.URL.Path == "/500" { w.WriteHeader(500) fmt.Fprintln(w, "Hello error!") } else { w.WriteHeader(200) fmt.Fprintln(w, "Hello world!") } })) }

func makeRequests(appURL string) { // make sure we always dial the same IP addresss for testing purposes because // circuit breaker state is applied on each ngrok edge server individually u, _ := url.Parse(appURL) addrs, err := net.LookupHost(u.Host) if err != nil { log.Fatal(err) } httpClient := http.Client{Transport: &http.Transport{ Dial: func(network, _ string) (net.Conn, error) { return net.Dial(network, addrs[0]+":443") }, }}

// make requests that return a 500 until the circuit opens
for {
	resp, err := httpClient.Get(appURL + "/500")
	if err != nil {
		log.Fatal(err)
	}
	fmt.Printf("Status Code %d\n", resp.StatusCode)
	if resp.StatusCode == 503 {
		fmt.Println("Circuit opened")
		break
	}
}

// make requests that will eventually return a 200 which will close the circuit
for {
	resp, err := httpClient.Get(appURL)
	if err != nil {
		log.Fatal(err)
	}
	fmt.Printf("Status Code %d\n", resp.StatusCode)
	if resp.StatusCode != 503 {
		fmt.Println("Circuit closed")
		os.Exit(0)
	}
}
export NGROK_AUTHTOKEN="<2dvYx8b2Jxcr6rQ7rMK4g0f5lxd_6MRbqiQJdYkspcWN1vb65>" go mod init example.com/ngrok-circuit-breaker go get golang.ngrok.com/ngrok go run example.go import ngrok

listener = ngrok.forward("localhost:8080", authtoken_from_env=True, verify_webhook_provider="twilio", verify_webhook_secret="{twilio signing secret}")

print(f"Ingress established at: {listener.url()}");

git clone https://github.com/ngrok/ngrok-webhook-nodejs-sample.git cd ngrok-webhook-nodejs-sample npm install npm start ngrok http 3000

ngrok http 3000 --verify-webhook stripe --verify-webhook-secret {whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS}

authtoken: 4nq9771bPxe8ctg7LKr_2ClH7Y15Zqe4bWLWF9p api_key: 24yRd5U3DestCQapJrrVHLOqiAC_7RviwRqpd3wc9dKLujQZN connect_timeout: 30s console_ui: true console_ui_color: transparent dns_resolver_ips:

1.1.1.1
8.8.8.8 heartbeat_interval: 1m heartbeat_tolerance: 5s inspect_db_size: 104857600 # 100mb inspect_db_size: 50000000 log_level: info log_format: json log: /var/log/ngrok.log metadata: '{"serial": "00012xa-33rUtz9", "comment": "For customer alan@example.com"}' proxy_url: socks5://localhost:9150 region: us remote_management: false root_cas: trusted update_channel: stable update_check: false version: 2 web_addr: localhost:4040 tunnels: website: addr: 8888 basic_auth:
"bob:bobpassword" schemes:
https host_header: "myapp.ngrok.dev" inspect: false proto: http domain: myapp.ngrok.dev
e2etls: addr: 9000 proto: tls domain: myapp.example.com crt: example.crt key: example.key

policyenforced: policy: inbound: - name: LimitIPs expressions: - "conn.ClientIP != '1.1.1.1'" actions: - type: deny addr: 8000 proto: tcp

ssh-access: addr: 22 proto: tcp remote_addr: 1.tcp.ngrok.io:12345

my-load-balanced-website: labels: - env=prod - team=infra addr: 8000

tunnels:
httpbin: proto: http addr: 8000 domain: alan-httpbin.ngrok.dev demo: proto: http addr: 9090 domain: demo.inconshreveable.com inspect: false ngrok start httpbin

tunnels: my-cool-website: labels: - env=prod - team=infra addr: 8000 inspect: false ssh-tunnel: labels: - hostname=my-hostname - service=ssh - team=development addr: 22 api_key: 24yRd5U3DestCQapJrrVHLOqiAC_7RviwRqpd3wc9dKLujQZN authtoken: 4nq9771bPxe8ctg7LKr_2ClH7Y15Zqe4bWLWF9p

log: /var/log/ngrok.log

metadata

This is a user-supplied custom string that will be returned as part of the ngrok API response to the list online sessions resource for all tunnels started by this agent. This is a useful mechanism to identify tunnels by your own device or customer identifier. Maximum 4096 characters.

metadata: bad8c1c0-8fce-11e4-b4a9-0800200c9a66

web_allow_hosts:

8.8.8.8
example.com curl http://localhost:4040/api/
{ "tunnels": [ { "name": "command_line", "uri": "/api/tunnels/command_line", "public_url": "https://d95211d2.ngrok.io", "proto": "https", "config": { "addr": "localhost:80", "inspect": true, }, "metrics": { "conns": { "count": 0, "gauge": 0, "rate1": 0, "rate5": 0, "rate15": 0, "p50": 0, "p90": 0, "p95": 0, "p99": 0 }, "http": { "count": 0, "rate1": 0, "rate5": 0, "rate15": 0, "p50": 0, "p90": 0, "p95": 0, "p99": 0 } } }, ... ], "uri": "/api/tunnels" } { "addr": "22", "proto": "tcp", "name": "ssh" }

{ "name": "", "uri": "/api/tunnels/", "public_url": "tcp://0.tcp.ngrok.io:53476", "proto": "tcp", "config": { "addr": "localhost:22", "inspect": false, }, "metrics": { "conns": { "count": 0, "gauge": 0, "rate1": 0, "rate5": 0, "rate15": 0, "p50": 0, "p90": 0, "p95": 0, "p99": 0 }, "http": { "count": 0, "rate1": 0, "rate5": 0, "rate15": 0, "p50": 0, "p90": 0, "p95": 0, "p99": 0 } } }

{ "name": "command_line", "uri": "/api/tunnels/command_line", "public_url": "https://ac294125.ngrok.io", "proto": "https", "config": { "addr": "localhost:80", "inspect": true, }, "metrics": { "conns": { "count": 0, "gauge": 0, "rate1": 0, "rate5": 0, "rate15": 0, "p50": 0, "p90": 0, "p95": 0, "p99": 0 }, "http": { "count": 0, "rate1": 0, "rate5": 0, "rate15": 0, "p50": 0, "p90": 0, "p95": 0, "p99": 0 } } } BHAHZGCJZK3BEVS7IRGZMKDF6USLO runner token apply to all commands

stripe login --api-key sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq

stripe login

stripe trigger payment_intent.succeeded

Secret key

pst_test_YWNjdF8xTTJKVGtMa2RJd0h1N2l4LE81ZEdIalZ6NlVuMUdjM3c3WkRnN0ZYRHZxRURwTXo_00gNK2DWAV run payment id

po_1OZNhvGF83d3fsgWC9jdBgcQ

run bank data DJqIeyHlhjb55r0K Routing number 031101279 ID ba_1OR7BGGF83d3fsgWxwDM4lDf

$ Stripe endpoint we_1Ova66GF83d3fsgW2nbowkDw Webhook signing secret: whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS

why?

req_3SnomkF11VBTwG

The payment failed. { "consent": { "terms_of_service": "accepted" }, "eid": "**", "expected_amount": "100000", "expected_payment_method_type": "link", "guid": "14b84001-905a-42f3-9e2b-18a9ebf0e15c540853", "init_checksum": "MXofbfTYAaKG1no6FZxkzMndcSrERGp3", "js_checksum": "qtod^n0=QU>azbu]Vn<D\^vUO[_esYxY=dwUca$<P<m^o?U^w", "key": "pk_live_*********************************************************************************************k76MVR", "last_displayed_line_item_group_details": { "shipping_rate_amount": "0", "subtotal": "100000", "total_discount_amount": "0", "total_exclusive_tax": "0", "total_inclusive_tax": "0" }, "muid": "eb78b5f0-bdd7-45f9-a924-dcf3e95a1a647d0ae4", "passive_captcha_ekey": "", "passive_captcha_token": "P1_eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJwYXNza2V5IjoibGxxQlR1SURGNkd1WWhCWTh4N1RXY2dLbWJHYUhpdk5DeTZBMDdPTnZ4NUNqdy9XcDkrR0hJTHo0bDdUbHFGSmVjSkNpSFR3N1AyVnZwVHh5RlUyVlgyL0lyZHVCZkc2eTd3RE9tTFRHcUsvUEwxK2V2SWpQcEhwNFRCaVJMaVV2eURPRG4wWnFPa1pONS9NNXVka0dsNER2R3E4djNaMHEvRXRESWZ0ZllNZTBCRVFZTklIU1dROXY3QVRZWHMxWUwvRXhQK3pubmlDUHkvOTQ3Z0kxdjd1Zzk1cG8ycnJGS0ErK2FKeHJsR3lnb3JzRTUwaVNtYm1mNlJuUURPYWcvbWh2OE9GNXg0bE1KMXVNdUw0Rm1UQzNpS2lMell3eDUyNDc2QWlvdEw4aEEzWWVYbEJySkdlT3lxSVRtaytraWY1M05Xd2VjdDY0KytnM3NGL0UrMjg4a04vSUFIQ0FEdEYxbU1vZEFSTjZjL3pvMlBTYUFtdGUzTVV5TTJXT09ZTENWM01VOHRhOHk0emc0d0txSXg0U3lKemxwcCtXVTRvRy9DU0ZRNXYwa29iNVBPMnJtc3QxTkVQT3ozMlNUQ1BFUkZReFdXeWtBaVErc01QbFVmZmhsYnBEcldrMnF6VEQxR0dxQ254MksxeExvYUlhVW5yWWxyNXFZZTVLVHJ4bnNQNUlDVTNrNjBlWVdwbzZBVVJCaGFiOE4rK1g3TEpuRzlLRmJTM2YxM2R5dDM5MlA1WTJZcEFGYUxnT0laSnppSjJOZHkvMXRxbURucFZXaVZrRG1xSjZJRU5UNTh4Y0NvS1oyRjRqVWtGSk5DVWRaejZYdVpLMHY5bGhtRmxoZGRSNGdjVWZQWWFtUjAwUG5wL3c5dXAySkF4UDRRc2RjN2RHUWhCOFJrL0NSVVdFTll5NEFLbXBLeldsMlNscy9SOEpUQUdraGRFdTZvbjNBb2Z5NmZJbC9kK0NCYzlwYjBHeDhaaU9qUmZFbjVMSWNBTUN0Ymp0TFkwaURWWFdQZUM1UUtaMUF1c051TVk2L1lVdFhNZk03eUNyeUVBMG45ajNlYy9hbk9zT01WUWxlWkFDT3RjRmx1KzIvVmlpUDVORG14VGRZc2R4MWU4VFR0MWFpL05IRmxVNXh4cGVmMEFldkx2NXRmWW41WTkxeU1vdGlZaXhvMnhFWkp6NmgycHZRVnpIVnN4aDNNeFRWMWlOZ1kySHVXbVNPbTZjOWdBRWtGZkZCSVM3V2VwY2g2Tng0TzlFVWh0VnpXaW5KRDFvNXZlYkdGMnBJakVYR0lSWVZNSCtWbnJaM2t1V2djOUpiRWtyYStiRjBkd0pxY2F2VityRkdqOW9ENFFSZkMwNmpSMzlvdU5CTmVzSU8xNWRFVE9TdDRHOGxMaUJ4QkhyL283VnR6bHZ2djdhbFI3K3VidlNXdlQ2QlI4cjdOQmxXR3BOM0lCRllnby96a0VJUmRnN0Fzb3RKWndPZENGdnBSbWhDYWJKVklzZTlwSXlrTWl3WGYvUnpTU2wzdkJiMSs4UDBtbFVkNEVCZS9CTnNTcmF4Nm9NWEVmR1c0N29YNFBmMTlqcm9qWnhyaDBOOWJ1b04yWlF0QWQwU255ZndQNUZYYTh2dWp0OGtrUXNlRHZaWVpCRi9TSW1BM2ZRdmM3VnZ5YVNSQktabHBzdFlzMElzYVhpU1pGbFg3NUdrbFVpZWNSREdleFROQVpObWtlN0lTbm4xbVpJaFpUOVlhN1RIdU0yM2dReEs3RnlFcUlzcjNadjYwVDBOSHptdk5lN0w0NkFudDFSbEIxZWQxWW1VN3pvVzdXbGZpOUc0MTZXZ28wQloyUDR6K1hmTXFQc2cwTFdKTytZVFI4Ym0wVzFpQ0ZEdWpUM3l5RGJJN0JWUTlwWDlEMnRjVXE0ajlpSTZjZktrb0d3Z2tCa1dtRmFuQ0QvV3BjTmVnSkJCMEJ0WHR2Z2NSeGQwbmpxR3F2aXIrZGF1TTlNZ0lrZDNLeHNCVXJkd2tySVJhOElvaDlCQmlkUDJMY0pkU1RWUittdFBMRW1iaWZoZVh5clRybUtEcEEvVnNCSmc2MEpBNXp3Q1E5NTlWWWQ5TFh5VnFhdnlrMzRwTC9NaTBPL1dnWmllbUhUNGFVSDdZVG5TekxMYmFQdW1aYVdpMkt4RFFkWmY0cW96akVya21iVnFOSk1XbXYzd2E3QkZhNzdyY0E2RjdXQmRUVkt0V0pqeXp0WWpyTHllNEpST0tsQlh1WmtxbVpnOGNsQlFoNGJobTI4c1FtQzI3UlBkM0dEMGwwTTFyMGpsZitpWDVLc3JGTitHNFJPMzFLT2ZNM2o1ajVzQzBaYytDa2JaNklwK1VKVmk2RmRESUFoMU5LOTl6eWhZR2QwMzlVU2FqdU02TmQxeG4zMTYxVUJQZGpkTFZpb3pFUFZqdXpEZUN6QXNmcDJWUTZyS1JmWUFjNEtVeVdmaEExTThUVHVXL1pJUW5ja2gzUm9UVm5JVE81bkh1YXNGYitYVEJZL0FaOEJzVjRkanFMdUVHc01YQThoV0FYMGxrejJXN1VWZVVINFpHald0T0d0SHZBZURJOTJiT0V4OXk0YWhrWU93czYyWURHL1F5c1FNc2pFWFMzb3d4ekcvNVBZaVJ6RlAwaDFYS09McXhNdmYrM2NlYlN3UkNOdkhMV2tYT2k1bk82TzROait5OGR2UGhVSWVBS0tWTTBGTmw5UW1XNzBFTEdPZjVOZzdWZGRBY3RWd3VsOUo0elAyUGhsOFF5bi8xK1l2bFpXMmpHUmQ3eXd2cUZVVVlPU2htNkk2VFB2eG4vVCtKWHJ4WUlaMmVnbVoyVy91UEhXbVFucGtZUUYzaEhIYnlkbnhDOEpGa2E3NGJNQjZRR3J0VHBvaGhUOFo1U0lXU1Iwbkt3UHhBOGdZaThDRlhKRXErcFpkT1RNYUhiay9RcDJmMFFCQXA4aEpKMU5IUWdrRCtZdEFBTnV5bWR5YW90RmJQeS9STnJyS1AyOTZiUlF5SVV4aU10dlo2Z1piMFRqK252WTRUVFU4UzNNWW14Nysrd242N1Rxcm11Zytjc3FMNEJVdnhmdGlCWnI3b0M1cnNmRFQ5d21XSS8iLCJleHAiOjE3MTA3NDI1OTksInNoYXJkX2lkIjo4MzM0NDA4OTcsInBkIjowLCJjZGF0YSI6IjRKOGNUeDBPRjd6byszdzB1WHNtZ0dzSEpubE5Geml0VUZON0dhYWNzQWpFdWZsbmlta3lydXpwT2FGVnl5S2hXSk9tVmdwcEdtOFZtMWNWOWJnL3BacDhHcDVmN1N0ZEpvTlU5M0JhaHRKbmE4V2pNZkVEWnp0QUUwTXRMQ0Qxb1Z2dzc4SDlJREdqK0FmTXVaZFp0OFpiT0JmZ1dmZUluRVVLNUx0dHhnOGtaUU93dW91S0ExTmxRamxiQk9vM1NGT1ZFdERPdTlESjdsN2JZL0x0OU9KME9NNTBZTjQ9VkpFeHI4ZHFFQWpuenI1UiJ9.pPcNQ2Y328R8U7Sar4Z5U0GO9y1caCAAPmbIy3aCnYo", "payment_method": "pm_1OvZUOGF83d3fsgWiXYpUHQh", "rv_timestamp": "qto>n<Q=U&CyY&>X^r<YNr<YN<Y_C<Y_C<Y^zY_<Y^n{U>o&U&CyY=P=eODdbL%e&areOMrY=n=YxnDd_Mv[bL>[OTCdOaveu%euUyX%n{U>e&U&Cyd&auY_n=d&;;X_d%d&UxdRP#[bd#exQxX=L&X&n%eu\\$ex]sY&ovXOUu[_$reunDd&osd=MueOP;d&<yY_<sX^o?U^w", "sid": "f931f0fd-f83a-4921-903f-45f5b359d9925f3b2a", "version": "2d3a08de7b" }

pip3 install stripe python3 -m flask run --port=4242 python3 -m flask run --port=4242 $ stripe listen --forward-to localhost:4242/webhook $ stripe trigger payment_intent.succeeded #! /usr/bin/env python3.6

Python 3.6 or newer required.

import json import os import stripe

This is your test secret API key.

stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

#! /usr/bin/env python3.6

Python 3.6 or newer required.

import json import os import stripe

This is your test secret API key.

stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

Replace this endpoint secret with your endpoint's unique secret

If you are testing with the CLI, find the secret by running 'stripe listen'

If you are using an endpoint defined with the API or dashboard, look in your webhook settings

at https://dashboard.stripe.com/webhooks

endpoint_secret = 'whsec_...' from flask import Flask, jsonify, request

app = Flask(name)

@app.route('/webhook', methods=['POST']) def webhook(): event = None payload = request.data

try:
    event = json.loads(payload)
except json.decoder.JSONDecodeError as e:
    print('⚠️  Webhook error while parsing basic request.' + str(e))
    return jsonify(success=False)
if endpoint_secret:
    # Only verify the event if there is an endpoint secret defined
    # Otherwise use the basic event deserialized with json
    sig_header = request.headers.get('stripe-signature')
    try:
        event = stripe.Webhook.construct_event(
            payload, sig_header, endpoint_secret
        )
    except stripe.error.SignatureVerificationError as e:
        print('⚠️  Webhook signature verification failed.' + str(e))
        return jsonify(success=False)

# Handle the event
if event and event['type'] == 'payment_intent.succeeded':
    payment_intent = event['data']['object']  # contains a stripe.PaymentIntent
    print('Payment for {} succeeded'.format(payment_intent['amount']))
    # Then define and call a method to handle the successful payment intent.
    # handle_payment_intent_succeeded(payment_intent)
elif event['type'] == 'payment_method.attached':
    payment_method = event['data']['object']  # contains a stripe.PaymentMethod
    # Then define and call a method to handle the successful attachment of a PaymentMethod.
    # handle_payment_method_attached(payment_method)
else:
    # Unexpected event type
    print('Unhandled event type {}'.format(event['type']))

return jsonify(success=True)
Run

https://dashboard.stripe.com/test/payouts/po_1OZNhvGF83d3fsgWC9jdBgcQ#wb-N4Igdghgbglg5hALjA9mEAuUEDGyoCmAKhAEaYgAmBAzspMmjSADQiJkASMdKATgE9MAbQC6bPigCuiAt16CRogL5saMAF4wwcTGCkAbA2wAWBeCcQUA7AAYoJ1iFjrSMAzEQCAsimoUXGFIDAidqOm0kVDBmLBAaAhC8AkoASUoKAHcCAH0ARgB5KAgANhKAcQAxAA4AZkpagDMaOAB1ACYwUhRMgGsAEUynDnIMEAJCMERmNgmCKdjQRvdZPkX4ggg+HEcxpzokKVixCVppbdC9thRSACsCPHSKJzmpogEAB0uQF75JPneXyUbEoSEuwGUqg2SVkaQyGH0RjUiQesIAgohZABbD6IJ4IwwGSHKIA

Download Stripe client secret

const {client_secret: seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ/ } = await res.json();

const {error} = await stripe.confirmPayment({ //Elements instance that was used to create the Payment Element elements, clientSecret, confirmParams: { return_url: 'https://example.com/order/123/complete', }, });

if (error) { // This point will only be reached if there is an immediate error when // confirming the payment. Show error to your customer (for example, payment // details incomplete) setErrorMessage(error.message); } else { // Your customer will be redirected to your return_url. For some payment // methods like iDEAL, your customer will be redirected to an intermediate // site first to authorize the payment, then redirected to the return_url. } import stripe stripe.api_key = "sk_test_51OR5eP...OF00CdDfT6Xqsk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq" stripe.Event.list(limit=3) RESPONSE { "object": "list", "url": "/v1/events", "has_more": false, "data": [ { "id": "evt_1NG8Du2eZvKYlo2CUI79vXWy", "object": "event", "api_version": "2019-02-19", "created": 1686089970, "data": { "object": { "id": "seti_1NG8Du2eZvKYlo2C9XMqbR0x", "object": "setup_intent", "application": null, "automatic_payment_methods": null, "cancellation_reason": null, "client_secret": "seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ", "created": 1686089970, "customer": null, "description": null, "flow_directions": null, "last_setup_error": null, "latest_attempt": null, "livemode": false, "mandate": null, "metadata": {}, "next_action": null, "on_behalf_of": null, "payment_method": "pm_1NG8Du2eZvKYlo2CYzzldNr7", "payment_method_options": { "acss_debit": { "currency": "cad", "mandate_options": { "interval_description": "First day of every month", "payment_schedule": "interval", "transaction_type": "personal" }, "verification_method": "automatic" } }, "payment_method_types": [ "acss_debit" ], "single_use_mandate": null, "status": "requires_confirmation", "usage": "off_session" } }, "livemode": false, "pending_webhooks": 0, "request": { "id": null, "idempotency_key": null }, "type": "setup_intent.created" } {...} {...} ], }

OK ID req_ZIIVfKfNp6QrOh

const {client_secret: seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ} = await res.json();

const {error} = await stripe.confirmPayment({ //Elements instance that was used to create the Payment Element elements, clientSecret, confirmParams: { return_url: 'https://example.com/order/123/complete', }, });

if (error) { // This point will only be reached if there is an immediate error when // confirming the payment. Show error to your customer (for example, payment // details incomplete) setErrorMessage(error.message); } else { // Your customer will be redirected to your return_url. For some payment // methods like iDEAL, your customer will be redirected to an intermediate // site first to authorize the payment, then redirected to the return_url. } import stripe stripe.api_key = "sk_test_51OR5eP...OF00CdDfT6Xqsk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq" stripe.Event.list(limit=3) RESPONSE { "object": "list", "url": "/v1/events", "has_more": false, "data": [ { "id": "evt_1NG8Du2eZvKYlo2CUI79vXWy", "object": "event", "api_version": "2019-02-19", "created": 1686089970, "data": { "object": { "id": "seti_1NG8Du2eZvKYlo2C9XMqbR0x", "object": "setup_intent", "application": null, "automatic_payment_methods": null, "cancellation_reason": null, "client_secret": "seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ", "created": 1686089970, "customer": null, "description": null, "flow_directions": null, "last_setup_error": null, "latest_attempt": null, "livemode": false, "mandate": null, "metadata": {}, "next_action": null, "on_behalf_of": null, "payment_method": "pm_1NG8Du2eZvKYlo2CYzzldNr7", "payment_method_options": { "acss_debit": { "currency": "cad", "mandate_options": { "interval_description": "First day of every month", "payment_schedule": "interval", "transaction_type": "personal" }, "verification_method": "automatic" } }, "payment_method_types": [ "acss_debit" ], "single_use_mandate": null, "status": "requires_confirmation", "usage": "off_session" } }, "livemode": false, "pending_webhooks": 0, "request": { "id": null, "idempotency_key": 6f5410cb-1ecc-4302-8130-baf8dd8c0a50 }, "type": "setup_intent.created" } {...} {...} ], }

stripe .retrieveSetupIntent( '{fcsess_client_secret_KRJTKvCY3IKoYTrW18EazcO3 /seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ }', ) .then(function(result) { // Handle result.error or result.paymentIntent }); stripe.collectFinancialConnectionsAccounts({ clientSecret: '{fcsess_client_secret_KRJTKvCY3IKoYTrW18EazcO3}' }) .then(function(result) { if (result.error) { // Inform the customer that there was an error. console.log(result.error.message);

// Handle next step based on length of accounts array
} else if (result.financialConnectionsSession.accounts.length === 0) {
  console.log('No accounts were linked');
} else {
  console.log(result.financialConnectionsSession.accounts)
}
});

{ "object": "customer_session", "client_secret": "_POpxYpmkXdtttYtZQYhrsOJZ2RCQ9kCqqXRU6qrP5c4Jgje", "components": { "buy_button": { "enabled": false }, "pricing_table": { "enabled": true } }, "customer": "cus_PO34b57IOUb83c", "expires_at": 1684790027, "livemode": false } { "object": "customer_session", "client_secret": "_POpxYpmkXdtttYtZQYhrsOJZ2RCQ9kCqqXRU6qrP5c4Jgje", "components": { "buy_button": { "enabled": false }, "pricing_table": { "enabled": true } }, "customer": "cus_PO34b57IOUb83c", "expires_at": 1684790027, "livemode": false }

Create a folder $ mkdir actions-runner && cd actions-runner

Download the latest runner package $ curl -o actions-runner-osx-x64-2.314.1.tar.gz -L https://github.com/actions/runner/releases/download/v2.314.1/actions-runner-osx-x64-2.314.1.tar.gz

Optional: Validate the hash $ echo "3faff4667d6d12c41da962580168415d628e3ffba9924b9ac995752087efc921 actions-runner-osx-x64-2.314.1.tar.gz" | shasum -a 256 -c

Extract the installer $ tar xzf ./actions-runner-osx-x64-2.314.1.tar.gz Configure

Create the runner and start the configuration experience $ ./config.sh --url https://github.com/grateful345/Wiz-Go-call-sign --token BHAHZGDHHICG3LFF53OICRLF6UR24

Last step, run it! $ ./run.sh Using your self-hosted runner

Use this YAML in your workflow file for each job runs-on: self-hosted

Orginization ID: e3ff35d1-cea4-4508-acb5-99d9cbd91e80


pk_live_51OR5ePGF83d3fsgW22PwNtYiShCVYIsrzZq2WxlxN2UAaB2qEIu0aUFJzjJxPtNT3rAs0Rvdo9XIVPb7rRMaeo3W00ALk76MVR PUBLISHABLE KEY LIVE

sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq secret test key STRIPE
[12:45 AM]
pk_test_51OR5ePGF83d3fsgWcl7ad29rrqOUNvjdYXN1JrElZlEyDloYQpFPuxSeRZH8KiCgvshlSaDYnuu1xxYiiWOCHj7W00Nrph1csX PUBLISHABLE KEY TEST


pk_live_51OR5ePGF83d3fsgW22PwNtYiShCVYIsrzZq2WxlxN2UAaB2qEIu0aUFJzjJxPtNT3rAs0Rvdo9XIVPb7rRMaeo3W00ALk76MVR

o5 council mainframe Ai — 03/17/2024 11:02 PM
print(f"Success! Here is your starter subscription product id: {starter_subscription.id}") print(f"Success! Here is your starter subscription price id: {starter_subscription_price.id}") python3 create_price.py Success! Here is your starter subscription product id: prod_0KxBDl589O8KAxCG1alJgiA6 Success! Here is your starter subscription price id: price_0KxBDm589O8KAxCGMgG7scjb stripe events resend evt_1OpkWDGF83d3fsgWRuQHTout { "id": "evt_1OpkWDGF83d3fsgWRuQHTout", "object": "event", "api_version": "2023-10-16", "created": 1709354993, "data": { "object": { "id": "clock_1OpkVpGF83d3fsgWXAn5JwxT", "object": "test_helpers.test_clock", "created": 1709354969, "deletes_after": 1711946969, "frozen_time": 1709354959, "livemode": false, "name": "10 day", "status": "ready" } }, "livemode": false, "pending_webhooks": 0, "request": { "id": "req_h41wlESGApv90k", "idempotency_key": null }, "type": "test_helpers.test_clock.deleted" } stripe charges --help

o5 council mainframe Ai — 03/17/2024 11:55 PM
"masked_api_key": "*9e2a1"
  }
March 18, 2024

o5 council mainframe Ai — Yesterday at 12:01 AM


o5 council mainframe Ai — Yesterday at 12:47 AM
"masked_api_key": "*9e2a1"
  }
[12:49 AM]
AF0F3FCCE9EE2011EF183E67AD67D6F299326E1E2F1B8DA8567F9FDA006F78F6 DUO SECRET KEY
[12:50 AM]
sH9wUncg7GsTTGIe7ydnISPHHbxZeUd7TspSmGk2  DUO SECRET KEY
[12:51 AM]
DIFRJUINL7UM749ZLTCJ INTEGRATION KEY
[12:51 AM]
api-8f5baae1.duosecurity.com
[12:53 AM]
73.44.108.236 IP ADDRESS

o5 council mainframe Ai — Yesterday at 1:03 AM

o5 council mainframe Ai — 02/25/2024 1:30 AM
stripe.Product.modify(
  "prod_NWjs8kKbJWmuuc",
  metadata={"order_id": "6735"}
[1:35 AM]... (1 KB left)
Expand
message.txt
51 KB

o5 council mainframe Ai — Yesterday at 1:10 AM
https://buy.stripe.com/3cscMY617bed7bWdRh
[1:13 AM]
https://buy.stripe.com/3cscMY617bed7bWdRh?client_reference_id=1000&prefilled_email=god964v%40gmail.com&prefilled_promo_code=1000
[1:16 AM]
Secret key
pst_test_YWNjdF8xTTJKVGtMa2RJd0h1N2l4LE81ZEdIalZ6NlVuMUdjM3c3WkRnN0ZYRHZxRURwTXo_00gNK2DWAV

o5 council mainframe Ai — Yesterday at 1:20 AM
$ ./config.sh --url https://github.com/grateful345/Wiz-Go-call-sign --token BHAHZGCJZK3BEVS7IRGZMKDF6USLO
GitHub
GitHub - grateful345/Wiz-Go-call-sign
Contribute to grateful345/Wiz-Go-call-sign development by creating an account on GitHub.

[1:23 AM]
BHAHZGCJZK3BEVS7IRGZMKDF6USLO.   Runner tokens BHAHZGDHHICG3LFF53OICRLF6UR24
[1:25 AM]

[1:27 AM]
<script async
  src="https://js.stripe.com/v3/buy-button.js">
</script>

<stripe-buy-button
  buy-button-id="buy_btn_1OvZeLGF83d3fsgWAamtMu9r"
  publishable-key="pk_live_51OR5ePGF83d3fsgW22PwNtYiShCVYIsrzZq2WxlxN2UAaB2qEIu0aUFJzjJxPtNT3rAs0Rvdo9XIVPb7rRMaeo3W00ALk76MVR"
>
</stripe-buy-button>

o5 council mainframe Ai — Yesterday at 1:34 AM
https://buy.stripe.com/3cscMY617bed7bWdRh

o5 council mainframe Ai — Yesterday at 1:45 AM
DJqIeyHlhjb55r0K
Routing number
031101279
ID
ba_1OR7BGGF83d3fsgWxwDM4lDf
[1:46 AM]
po_1OZNhvGF83d3fsgWC9jdBgcQ

o5 council mainframe Ai — Yesterday at 1:56 AM
we_1Ova66GF83d3fsgW2nbowkDw
 Stripe endpoint
[1:57 AM]
https://dashboard.stripe.com/test/payouts/po_1OZNhvGF83d3fsgWC9jdBgcQ#wb-N4Igdghgbglg5hALjA9mEAuUEDGyoCmAKhAEaYgAmBAzspMmjSADQiJkASMdKATgE9MAbQC6bPigCuiAt16CRogL5saMAF4wwcTGCkAbA2wAWBeCcQUA7AAYoJ1iFjrSMAzEQCAsimoUXGFIDAidqOm0kVDBmLBAaAhC8AkoASUoKAHcCAH0ARgB5KAgANhKAcQAxAA4AZkpagDMaOAB1ACYwUhRMgGsAEUynDnIMEAJCMERmNgmCKdjQRvdZPkX4ggg+HEcxpzokKVixCVppbdC9thRSACsCPHSKJzmpogEAB0uQF75JPneXyUbEoSEuwGUqg2SVkaQyGH0RjUiQesIAgohZABbD6IJ4IwwGSHKIA
Stripe Login | Sign in to the Stripe Dashboard
Sign in to the Stripe Dashboard to manage business payments and operations in your account. Manage payments and refunds, respond to disputes and more.
[2:00 AM]
stripe login --api-key sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq

o5 council mainframe Ai — Yesterday at 2:04 AM
pip3 install stripe

o5 council mainframe Ai — Yesterday at 2:27 AM
Event details
evt_3OvZUOGF83d3fsgW0CVGOJLf (run it)
[2:31 AM]
whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS
[2:32 AM]
Webhook signing secret whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS


FILE:
evt_1OvyoVGF83d3fsgWW9GjCrme



{
  "object": {
    "id": "file_1OvyoVGF83d3fsgWJ2y8LUzQ",
    "object": "file",
    "created": 1710839911,
    "expires_at": null,
    "filename": "Untitled_20240318.csv",
    "links": {
      "object": "list",
      "data": [],
      "has_more": false,
      "url": "/v1/file_links?file=file_1OvyoVGF83d3fsgWJ2y8LUzQ"
    },
    "purpose": "sigma_scheduled_query",
    "size": 64,
    "title": "Untitled for 2024-03-18",
    "type": "csv",
    "url": "https://files.stripe.com/v1/files/file_1OvyoVGF83d3fsgWJ2y8LUzQ/contents"
  },
  "previous_attributes": null
}
Download
#! /usr/bin/env python3.6
# Python 3.6 or newer required.

import json
import os
import stripe
# This is your test secret API key.
stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

# Replace this endpoint secret with your endpoint's unique secret
# If you are testing with the CLI, find the secret by running 'stripe listen'
# If you are using an endpoint defined with the API or dashboard, look in your webhook settings
# at https://dashboard.stripe.com/webhooks
endpoint_secret = 'whsec_...'
from flask import Flask, jsonify, request

app = Flask(__name__)

@app.route('/webhook', methods=['POST'])
def webhook():
    event = None
    payload = request.data

    try:
        event = json.loads(payload)
    except json.decoder.JSONDecodeError as e:
        print('⚠️  Webhook error while parsing basic request.' + str(e))
        return jsonify(success=False)
    if endpoint_secret:
        # Only verify the event if there is an endpoint secret defined
        # Otherwise use the basic event deserialized with json
        sig_header = request.headers.get('stripe-signature')
        try:
            event = stripe.Webhook.construct_event(
                payload, sig_header, endpoint_secret
            )
        except stripe.error.SignatureVerificationError as e:
            print('⚠️  Webhook signature verification failed.' + str(e))
            return jsonify(success=False)

    # Handle the event
    if event and event['type'] == 'payment_intent.succeeded':
        payment_intent = event['data']['object']  # contains a stripe.PaymentIntent
        print('Payment for {} succeeded'.format(payment_intent['amount']))
        # Then define and call a method to handle the successful payment intent.
        # handle_payment_intent_succeeded(payment_intent)
    elif event['type'] == 'payment_method.attached':
        payment_method = event['data']['object']  # contains a stripe.PaymentMethod
        # Then define and call a method to handle the successful attachment of a PaymentMethod.
        # handle_payment_method_attached(payment_method)
    else:
        # Unexpected event type
        print('Unhandled event type {}'.format(event['type']))

    return jsonify(success=True)
[
](https://github.com/grateful345/AGENCY-WEBHOOK.git)https://github.com/grateful345/AGENCY-WEBHOOK.git
echo "# AGENCY-WEBHOOK" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/grateful345/AGENCY-WEBHOOK.git
git push -u origin main
…or push an existing repository from the command line
git remote add origin https://github.com/grateful345/AGENCY-WEBHOOK.git
git branch -M main
git push -u origin main
Install the Stripe Python package
Install the Stripe package and import it in your code. Alternatively, if you’re starting from scratch and need a requirements.txt file, download the project files using the link in the code editor.

pip

GitHub
Install the package via pip:
pip3 install stripe

Server
Create a new endpoint

settings
A webhook is an endpoint on your server that receives requests from Stripe, notifying you about events that happen on your account such as a customer disputing a charge or a successful recurring payment. Add a new endpoint to your server and make sure it’s publicly accessible so we can send unauthenticated POST requests.
Server
2
Handle requests from Stripe
Read the event data
Stripe sends the event data in the request body. Each event is structured as an Event object with a type, id, and related Stripe resource nested under data.
Server
Handle the event
As soon as you have the event object, check the type to know what kind of event happened. You can use one webhook to handle several different event types at once, or set up individual endpoints for specific events.
Server
Return a 200 response
Build and run your server to test the endpoint at http://localhost:4242/webhook.
python3 -m flask run --port=4242

Server
Download the CLI
Use the Stripe CLI to test your webhook locally. Download the CLI and log in with your Stripe account. Alternatively, use a service like ngrok to make your local endpoint publicly accessible.
stripe login

Run in the Stripe Shell
Server
Forward events to your webhook

settings
Set up event forwarding with the CLI to send all Stripe events in testmode to your local webhook endpoint.
stripe listen --forward-to localhost:4242/webhook

Run in the Stripe Shell
Server
Simulate events

settings
Use the CLI to simulate specific events that test your webhook application logic by sending a POST request to your webhook endpoint with a mocked Stripe event object.
stripe trigger payment_intent.succeeded

Run in the Stripe Shell
Server
Congratulations!

Stripe-Signature:
t=1492774577,
v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd,
v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39

You have a basic webhook endpoint ready to accept events from Stripe. Now add the application logic that your business needs to handle the events you care the most about. You can also extend your endpoint with the steps b
[
](https://<your-website>/<your-webhook-endpoint>)https://<your-website>/<[webhook](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862-endpoint>
README.md | 3 +++
1 file changed, 3 insertions(+)

diff --git a/README.md b/README.md
index 806cda8..9b1de77 100644
--- a/README.md
+++ b/README.md
@@ -121,3 +121,6 @@ Run in the Stripe Shell
Server
Congratulations!
You have a basic webhook endpoint ready to accept events from Stripe. Now add the application logic that your business needs to handle the events you care the most about. You can also extend your endpoint with the steps b
+
+https:///<webhookhttps://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862-endpoint>
# Set your secret key. Remember to switch to your live secret key in production.
# See your keys here: https://dashboard.stripe.com/apikeys
stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

endpoint = stripe.WebhookEndpoint.create(
  url='https://example.com/my/webhook/endpoint',
  enabled_events=[
    'payment_intent.payment_failed',
    'payment_intent.succeeded',
  ],
)
# Set your secret key. Remember to switch to your live secret key in production.
# See your keys here: https://dashboard.stripe.com/apikeys
stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

from django.http import HttpResponse

# If you are testing your webhook locally with the Stripe CLI you
# can find the endpoint's secret by running `stripe listen`
# Otherwise, find your endpoint's secret in your webhook settings in the Developer Dashboard
endpoint_secret = 'whsec_...'

# Using Django
@csrf_exempt
def my_webhook_view(request):
  payload = request.body
  sig_header = request.META['Stripe-Signature:
t=1492774577,
v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd,
v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39']
  event = None

  try:
    event = stripe.Webhook.construct_event(
      payload, sig_header, endpoint_secret
    )
  except ValueError as e:
    # Invalid payload
    print('Error parsing payload: {}'.format(str(e)))
    return HttpResponse(status=400)
  except stripe.error.SignatureVerificationError as e:
    # Invalid signature
    print('Error verifying webhook signature: {}'.format(str(e)))
    return HttpResponse(status=400)

  # Handle the event
  if event.type == 'payment_intent.succeeded':
    payment_intent = event.data.object # contains a stripe.PaymentIntent
    print('PaymentIntent was successful!')
  elif event.type == 'payment_method.attached':
    payment_method = event.data.object # contains a stripe.PaymentMethod
    print('PaymentMethod was attached to a Customer!')
  # ... handle other event types
  else:
    print('Unhandled event type {}'.format(event.type))
import json

# Webhooks are always sent as HTTP POST requests, so ensure
# that only POST requests reach your webhook view by
# decorating `webhook()` with `require_POST`.
#
# To ensure that the webhook view can receive webhooks,
# also decorate `webhook()` with `csrf_exempt`.
@require_POST
@csrf_exempt
def webhook(request):
import json
from django.http import HttpResponse

# Using Django
@csrf_exempt
def my_webhook_view(request):
  payload = request.body
  event = None

  try:
    event = stripe.Event.construct_from(
      json.loads(payload), stripe.api_key
    )
  except ValueError as e:
    # Invalid payload
    return HttpResponse(status=400)

  # Handle the event
  if event.type == 'payment_intent.succeeded':
    payment_intent = event.data.object # contains a stripe.PaymentIntent
    # Then define and call a method to handle the successful payment intent.
    # handle_payment_intent_succeeded(payment_intent)
  elif event.type == 'payment_method.attached':
    payment_method = event.data.object # contains a stripe.PaymentMethod
    # Then define and call a method to handle the successful attachment of a PaymentMethod.
    # handle_payment_method_attached(payment_method)
  # ... handle other event types
  else:
    print('Unhandled event type {}'.format(event.type))

  return HttpResponse(status=200)
stripe listen --forward-to localhost:4242/stripe_webhooks
stripe listen --events payment_intent.created,customer.created,payment_intent.succeeded,checkout.session.completed,payment_intent.payment_failed \
  --forward-to localhost:4242/webhook
stripe listen --load-from-webhooks-api --forward-to localhost:5000
Ready! Your webhook signing secret is '{{whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS}}' (^C to quit)


stripe trigger payment_intent.succeeded
Running fixture for: payment_intent
Trigger succeeded! Check dashboard for event details.
[
](https://<[your-website](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862>/<we_1Ova66GF83d3fsgW2nbowkDw>)
  # Process webhook data in `request.body`  return HttpResponse(status=200)
# Set your secret key. Remember to switch to your live secret key in production.
# See your keys here: https://dashboard.stripe.com/apikeys
stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

from django.http import HttpResponse

# If you are testing your webhook locally with the Stripe CLI you
# can find the endpoint's secret by running `stripe listen`
# Otherwise, find your endpoint's secret in your webhook settings in the Developer Dashboard
endpoint_secret = 'whsec_...'

# Using Django
@csrf_exempt
def my_webhook_view(request):
  payload = request.body
  sig_header = request.META['Stripe-Signature:
t=1492774577,
v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd,
v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39']
  event = None

  try:
    event = stripe.Webhook.construct_event(
      payload, sig_header, endpoint_secret
    )
  except ValueError as e:
    # Invalid payload
    print('Error parsing payload: {}'.format(str(e)))
    return HttpResponse(status=400)
  except stripe.error.SignatureVerificationError as e:
    # Invalid signature
    print('Error verifying webhook signature: {}'.format(str(e)))
    return HttpResponse(status=400)

  # Handle the event
  if event.type == 'payment_intent.succeeded':
    payment_intent = event.data.object # contains a stripe.PaymentIntent
    print('PaymentIntent was successful!')
  elif event.type == 'payment_method.attached':
    payment_method = event.data.object # contains a stripe.PaymentMethod
    print('PaymentMethod was attached to a Customer!')
  # ... handle other event types
  else:
    print('Unhandled event type {}'.format(event.type))

  return HttpResponse(status=200)
  import json

# Webhooks are always sent as HTTP POST requests, so ensure
# that only POST requests reach your webhook view by
# decorating `webhook()` with `require_POST`.
#
# To ensure that the webhook view can receive webhooks,
# also decorate `webhook()` with `csrf_exempt`.
@require_POST
@csrf_exempt
def webhook(request):
THE EVENT OBJECT
{
  "id": "evt_1NG8Du2eZvKYlo2CUI79vXWy",
  "object": "event",
  "api_version": "2019-02-19",
  "created": 1686089970,
  "data": {
    "object": {
      "id": "seti_1NG8Du2eZvKYlo2C9XMqbR0x",
      "object": "setup_intent",
      "application": null,
      "automatic_payment_methods": null,
      "cancellation_reason": null,
      "client_secret": "seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ",
      "created": 1686089970,
      "customer": null,
      "description": null,
      "flow_directions": null,
      "last_setup_error": null,
      "latest_attempt": null,
      "livemode": false,
      "mandate": null,
      "metadata": {},
      "next_action": null,
      "on_behalf_of": null,
      "payment_method": "pm_1NG8Du2eZvKYlo2CYzzldNr7",
      "payment_method_options": {
        "acss_debit": {
          "currency": "cad",
          "mandate_options": {
            "interval_description": "First day of every month",
            "payment_schedule": "interval",
            "transaction_type": "personal"
          },
          "verification_method": "automatic"
        }
      },
      "payment_method_types": [
        "acss_debit"
      ],
      "single_use_mandate": null,
      "status": "requires_confirmation",
      "usage": "off_session"
    }
  },
  "livemode": false,
  "pending_webhooks": 0,
  "request": {
    "id": null,
    "idempotency_key": null
  },
  "type": "setup_intent.created"


  # Process webhook data in `request.body`

  PATCH

# AGENCY-WEBHOOK

Download
#! /usr/bin/env python3.6
# Python 3.6 or newer required.

import json
import os
import stripe
# This is your test secret API key.
stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

# Replace this endpoint secret with your endpoint's unique secret
# If you are testing with the CLI, find the secret by running 'stripe listen'
# If you are using an endpoint defined with the API or dashboard, look in your webhook settings
# at https://dashboard.stripe.com/webhooks
endpoint_secret = 'whsec_...'
from flask import Flask, jsonify, request

app = Flask(__name__)

@app.route('/webhook', methods=['POST'])
def webhook():
    event = None
    payload = request.data

    try:
        event = json.loads(payload)
    except json.decoder.JSONDecodeError as e:
        print('⚠️  Webhook error while parsing basic request.' + str(e))
        return jsonify(success=False)
    if endpoint_secret:
        # Only verify the event if there is an endpoint secret defined
        # Otherwise use the basic event deserialized with json
        sig_header = request.headers.get('stripe-signature')
        try:
            event = stripe.Webhook.construct_event(
                payload, sig_header, endpoint_secret
            )
        except stripe.error.SignatureVerificationError as e:
            print('⚠️  Webhook signature verification failed.' + str(e))
            return jsonify(success=False)

    # Handle the event
    if event and event['type'] == 'payment_intent.succeeded':
        payment_intent = event['data']['object']  # contains a stripe.PaymentIntent
        print('Payment for {} succeeded'.format(payment_intent['amount']))
        # Then define and call a method to handle the successful payment intent.
        # handle_payment_intent_succeeded(payment_intent)
    elif event['type'] == 'payment_method.attached':
        payment_method = event['data']['object']  # contains a stripe.PaymentMethod
        # Then define and call a method to handle the successful attachment of a PaymentMethod.
        # handle_payment_method_attached(payment_method)
    else:
        # Unexpected event type
        print('Unhandled event type {}'.format(event['type']))

    return jsonify(success=True)
[
](https://github.com/grateful345/AGENCY-WEBHOOK.git)https://github.com/grateful345/AGENCY-WEBHOOK.git
echo "# AGENCY-WEBHOOK" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/grateful345/AGENCY-WEBHOOK.git
git push -u origin main
…or push an existing repository from the command line
git remote add origin https://github.com/grateful345/AGENCY-WEBHOOK.git
git branch -M main
git push -u origin main
Install the Stripe Python package
Install the Stripe package and import it in your code. Alternatively, if you’re starting from scratch and need a requirements.txt file, download the project files using the link in the code editor.

pip

GitHub
Install the package via pip:
pip3 install stripe

Server
Create a new endpoint

settings
A webhook is an endpoint on your server that receives requests from Stripe, notifying you about events that happen on your account such as a customer disputing a charge or a successful recurring payment. Add a new endpoint to your server and make sure it’s publicly accessible so we can send unauthenticated POST requests.
Server
2
Handle requests from Stripe
Read the event data
Stripe sends the event data in the request body. Each event is structured as an Event object with a type, id, and related Stripe resource nested under data.
Server
Handle the event
As soon as you have the event object, check the type to know what kind of event happened. You can use one webhook to handle several different event types at once, or set up individual endpoints for specific events.
Server
Return a 200 response
Build and run your server to test the endpoint at http://localhost:4242/webhook.
python3 -m flask run --port=4242

Server
Download the CLI
Use the Stripe CLI to test your webhook locally. Download the CLI and log in with your Stripe account. Alternatively, use a service like ngrok to make your local endpoint publicly accessible.
stripe login

Run in the Stripe Shell
Server
Forward events to your webhook

settings
Set up event forwarding with the CLI to send all Stripe events in testmode to your local webhook endpoint.
stripe listen --forward-to localhost:4242/webhook

Run in the Stripe Shell
Server
Simulate events

settings
Use the CLI to simulate specific events that test your webhook application logic by sending a POST request to your webhook endpoint with a mocked Stripe event object.
stripe trigger payment_intent.succeeded

Run in the Stripe Shell
Server
Congratulations!
Stripe-Signature:
t=1492774577,
v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd,
v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39

You have a basic webhook endpoint ready to accept events from Stripe. Now add the application logic that your business needs to handle the events you care the most about. You can also extend your endpoint with the steps b
[
](https://<your-website>/<your-webhook-endpoint>)https://<your-website>/<[webhook](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862-endpoint>
README.md | 3 +++
1 file changed, 3 insertions(+)

diff --git a/README.md b/README.md
index 806cda8..9b1de77 100644
--- a/README.md
+++ b/README.md
@@ -121,3 +121,6 @@ Run in the Stripe Shell
Server
Congratulations!
You have a basic webhook endpoint ready to accept events from Stripe. Now add the application logic that your business needs to handle the events you care the most about. You can also extend your endpoint with the steps b
+
+https:///<webhookhttps://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862-endpoint>
# Set your secret key. Remember to switch to your live secret key in production.
# See your keys here: https://dashboard.stripe.com/apikeys
stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

endpoint = stripe.WebhookEndpoint.create(
  url='https://example.com/my/webhook/endpoint',
  enabled_events=[
    'payment_intent.payment_failed',
    'payment_intent.succeeded',
  ],
)
# Set your secret key. Remember to switch to your live secret key in production.
# See your keys here: https://dashboard.stripe.com/apikeys
stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

from django.http import HttpResponse

# If you are testing your webhook locally with the Stripe CLI you
# can find the endpoint's secret by running `stripe listen`
# Otherwise, find your endpoint's secret in your webhook settings in the Developer Dashboard
endpoint_secret = 'whsec_...'

# Using Django
@csrf_exempt
def my_webhook_view(request):
  payload = request.body
  sig_header = request.META['Stripe-Signature:
t=1492774577,
v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd,
v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39']
  event = None

  try:
    event = stripe.Webhook.construct_event(
      payload, sig_header, endpoint_secret
    )
  except ValueError as e:
    # Invalid payload
    print('Error parsing payload: {}'.format(str(e)))
    return HttpResponse(status=400)
  except stripe.error.SignatureVerificationError as e:
    # Invalid signature
    print('Error verifying webhook signature: {}'.format(str(e)))
    return HttpResponse(status=400)

  # Handle the event
  if event.type == 'payment_intent.succeeded':
    payment_intent = event.data.object # contains a stripe.PaymentIntent
    print('PaymentIntent was successful!')
  elif event.type == 'payment_method.attached':
    payment_method = event.data.object # contains a stripe.PaymentMethod
    print('PaymentMethod was attached to a Customer!')
  # ... handle other event types
  else:
    print('Unhandled event type {}'.format(event.type))
import json

# Webhooks are always sent as HTTP POST requests, so ensure
# that only POST requests reach your webhook view by
# decorating `webhook()` with `require_POST`.
#
# To ensure that the webhook view can receive webhooks,
# also decorate `webhook()` with `csrf_exempt`.
@require_POST
@csrf_exempt
def webhook(request):
import json
from django.http import HttpResponse

# Using Django
@csrf_exempt
def my_webhook_view(request):
  payload = request.body
  event = None

  try:
    event = stripe.Event.construct_from(
      json.loads(payload), stripe.api_key
    )
  except ValueError as e:
    # Invalid payload
    return HttpResponse(status=400)

  # Handle the event
  if event.type == 'payment_intent.succeeded':
    payment_intent = event.data.object # contains a stripe.PaymentIntent
    # Then define and call a method to handle the successful payment intent.
    # handle_payment_intent_succeeded(payment_intent)
  elif event.type == 'payment_method.attached':
    payment_method = event.data.object # contains a stripe.PaymentMethod
    # Then define and call a method to handle the successful attachment of a PaymentMethod.
    # handle_payment_method_attached(payment_method)
  # ... handle other event types
  else:
    print('Unhandled event type {}'.format(event.type))

  return HttpResponse(status=200)
stripe listen --forward-to localhost:4242/stripe_webhooks
stripe listen --events payment_intent.created,customer.created,payment_intent.succeeded,checkout.session.completed,payment_intent.payment_failed \
  --forward-to localhost:4242/webhook
stripe listen --load-from-webhooks-api --forward-to localhost:5000
Ready! Your webhook signing secret is '{{whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS}}' (^C to quit)


stripe trigger payment_intent.succeeded
Running fixture for: payment_intent
Trigger succeeded! Check dashboard for event details.
[
](https://<[your-website](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862>/<we_1Ova66GF83d3fsgW2nbowkDw>)
  # Process webhook data in `request.body`  return HttpResponse(status=200)
# Set your secret key. Remember to switch to your live secret key in production.
# See your keys here: https://dashboard.stripe.com/apikeys
stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

from django.http import HttpResponse

# If you are testing your webhook locally with the Stripe CLI you
# can find the endpoint's secret by running `stripe listen`
# Otherwise, find your endpoint's secret in your webhook settings in the Developer Dashboard
endpoint_secret = 'whsec_...'

# Using Django
@csrf_exempt
def my_webhook_view(request):
  payload = request.body
  sig_header = request.META['Stripe-Signature:
t=1492774577,
v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd,
v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39']
  event = None

  try:
    event = stripe.Webhook.construct_event(
      payload, sig_header, endpoint_secret
    )
  except ValueError as e:
    # Invalid payload
    print('Error parsing payload: {}'.format(str(e)))
    return HttpResponse(status=400)
  except stripe.error.SignatureVerificationError as e:
    # Invalid signature
    print('Error verifying webhook signature: {}'.format(str(e)))
    return HttpResponse(status=400)

  # Handle the event
  if event.type == 'payment_intent.succeeded':
    payment_intent = event.data.object # contains a stripe.PaymentIntent
    print('PaymentIntent was successful!')
  elif event.type == 'payment_method.attached':
    payment_method = event.data.object # contains a stripe.PaymentMethod
    print('PaymentMethod was attached to a Customer!')
  # ... handle other event types
  else:
    print('Unhandled event type {}'.format(event.type))

  return HttpResponse(status=200)
  import json

# Webhooks are always sent as HTTP POST requests, so ensure
# that only POST requests reach your webhook view by
# decorating `webhook()` with `require_POST`.
#
# To ensure that the webhook view can receive webhooks,
# also decorate `webhook()` with `csrf_exempt`.
@require_POST
@csrf_exempt
def webhook(request):
THE EVENT OBJECT
{
  "id": "evt_1NG8Du2eZvKYlo2CUI79vXWy",
  "object": "event",
  "api_version": "2019-02-19",
  "created": 1686089970,
  "data": {
    "object": {
      "id": "seti_1NG8Du2eZvKYlo2C9XMqbR0x",
      "object": "setup_intent",
      "application": null,
      "automatic_payment_methods": null,
      "cancellation_reason": null,
      "client_secret": "seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ",
      "created": 1686089970,
      "customer": null,
      "description": null,
      "flow_directions": null,
      "last_setup_error": null,
      "latest_attempt": null,
      "livemode": false,
      "mandate": null,
      "metadata": {},
      "next_action": null,
      "on_behalf_of": null,
      "payment_method": "pm_1NG8Du2eZvKYlo2CYzzldNr7",
      "payment_method_options": {
        "acss_debit": {
          "currency": "cad",
          "mandate_options": {
            "interval_description": "First day of every month",
            "payment_schedule": "interval",
            "transaction_type": "personal"
          },
          "verification_method": "automatic"
        }
      },
      "payment_method_types": [
        "acss_debit"
      ],
      "single_use_mandate": null,
      "status": "requires_confirmation",
      "usage": "off_session"
    }
  },
  "livemode": false,
  "pending_webhooks": 0,
  "request": {
    "id": null,
    "idempotency_key": null
  },
  "type": "setup_intent.created"


  # Process webhook data in `request.body`
---
 README.md | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)

diff --git a/README.md b/README.md
index 1f3d7ba..1efe598 100644
--- a/README.md
+++ b/README.md
@@ -248,7 +248,7 @@ stripe trigger payment_intent.succeeded
 Running fixture for: payment_intent
 Trigger succeeded! Check dashboard for event details.
 [
-](https://<[your-website](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862>/<whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS>)
+](https://<[your-website](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862>/<we_1Ova66GF83d3fsgW2nbowkDw>)
   # Process webhook data in `request.body`  return HttpResponse(status=200)
 # Set your secret key. Remember to switch to your live secret key in production.
 # See your keys here: https://dashboard.stripe.com/apikeys

 Download
#! /usr/bin/env python3.6
# Python 3.6 or newer required.

import json
import os
import stripe
# This is your test secret API key.
stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

# Replace this endpoint secret with your endpoint's unique secret
# If you are testing with the CLI, find the secret by running 'stripe listen'
# If you are using an endpoint defined with the API or dashboard, look in your webhook settings
# at https://dashboard.stripe.com/webhooks
endpoint_secret = 'whsec_...'
from flask import Flask, jsonify, request

app = Flask(__name__)

@app.route('/webhook', methods=['POST'])
def webhook():
    event = None
    payload = request.data

    try:
        event = json.loads(payload)
    except json.decoder.JSONDecodeError as e:
        print('⚠️  Webhook error while parsing basic request.' + str(e))
        return jsonify(success=False)
    if endpoint_secret:
        # Only verify the event if there is an endpoint secret defined
        # Otherwise use the basic event deserialized with json
        sig_header = request.headers.get('stripe-signature')
        try:
            event = stripe.Webhook.construct_event(
                payload, sig_header, endpoint_secret
            )
        except stripe.error.SignatureVerificationError as e:
            print('⚠️  Webhook signature verification failed.' + str(e))
            return jsonify(success=False)

    # Handle the event
    if event and event['type'] == 'payment_intent.succeeded':
        payment_intent = event['data']['object']  # contains a stripe.PaymentIntent
        print('Payment for {} succeeded'.format(payment_intent['amount']))
        # Then define and call a method to handle the successful payment intent.
        # handle_payment_intent_succeeded(payment_intent)
    elif event['type'] == 'payment_method.attached':
        payment_method = event['data']['object']  # contains a stripe.PaymentMethod
        # Then define and call a method to handle the successful attachment of a PaymentMethod.
        # handle_payment_method_attached(payment_method)
    else:
        # Unexpected event type
        print('Unhandled event type {}'.format(event['type']))

    return jsonify(success=True)
[
](https://github.com/grateful345/AGENCY-WEBHOOK.git)https://github.com/grateful345/AGENCY-WEBHOOK.git
echo "# AGENCY-WEBHOOK" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/grateful345/AGENCY-WEBHOOK.git
git push -u origin main
…or push an existing repository from the command line
git remote add origin https://github.com/grateful345/AGENCY-WEBHOOK.git
git branch -M main
git push -u origin main
Install the Stripe Python package
Install the Stripe package and import it in your code. Alternatively, if you’re starting from scratch and need a requirements.txt file, download the project files using the link in the code editor.

pip

GitHub
Install the package via pip:
pip3 install stripe

Server
Create a new endpoint

settings
A webhook is an endpoint on your server that receives requests from Stripe, notifying you about events that happen on your account such as a customer disputing a charge or a successful recurring payment. Add a new endpoint to your server and make sure it’s publicly accessible so we can send unauthenticated POST requests.
Server
2
Handle requests from Stripe
Read the event data
Stripe sends the event data in the request body. Each event is structured as an Event object with a type, id, and related Stripe resource nested under data.
Server
Handle the event
As soon as you have the event object, check the type to know what kind of event happened. You can use one webhook to handle several different event types at once, or set up individual endpoints for specific events.
Server
Return a 200 response
Build and run your server to test the endpoint at http://localhost:4242/webhook.
python3 -m flask run --port=4242

Server
Download the CLI
Use the Stripe CLI to test your webhook locally. Download the CLI and log in with your Stripe account. Alternatively, use a service like ngrok to make your local endpoint publicly accessible.
stripe login

Run in the Stripe Shell
Server
Forward events to your webhook

settings
Set up event forwarding with the CLI to send all Stripe events in testmode to your local webhook endpoint.
stripe listen --forward-to localhost:4242/webhook

Run in the Stripe Shell
Server
Simulate events

settings
Use the CLI to simulate specific events that test your webhook application logic by sending a POST request to your webhook endpoint with a mocked Stripe event object.
stripe trigger payment_intent.succeeded

Run in the Stripe Shell
Server
Congratulations!
Stripe-Signature:
t=1492774577,
v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd,
v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39

You have a basic webhook endpoint ready to accept events from Stripe. Now add the application logic that your business needs to handle the events you care the most about. You can also extend your endpoint with the steps b
[
](https://<your-website>/<your-webhook-endpoint>)https://<your-website>/<[webhook](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862-endpoint>
README.md | 3 +++
1 file changed, 3 insertions(+)

diff --git a/README.md b/README.md
index 806cda8..9b1de77 100644
--- a/README.md
+++ b/README.md
@@ -121,3 +121,6 @@ Run in the Stripe Shell
Server
Congratulations!
You have a basic webhook endpoint ready to accept events from Stripe. Now add the application logic that your business needs to handle the events you care the most about. You can also extend your endpoint with the steps b
+
+https:///<webhookhttps://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862-endpoint>
# Set your secret key. Remember to switch to your live secret key in production.
# See your keys here: https://dashboard.stripe.com/apikeys
stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

endpoint = stripe.WebhookEndpoint.create(
  url='https://example.com/my/webhook/endpoint',
  enabled_events=[
    'payment_intent.payment_failed',
    'payment_intent.succeeded',
  ],
)
# Set your secret key. Remember to switch to your live secret key in production.
# See your keys here: https://dashboard.stripe.com/apikeys
stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

from django.http import HttpResponse

# If you are testing your webhook locally with the Stripe CLI you
# can find the endpoint's secret by running `stripe listen`
# Otherwise, find your endpoint's secret in your webhook settings in the Developer Dashboard
endpoint_secret = 'whsec_...'

# Using Django
@csrf_exempt
def my_webhook_view(request):
  payload = request.body
  sig_header = request.META['Stripe-Signature:
t=1492774577,
v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd,
v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39']
  event = None

  try:
    event = stripe.Webhook.construct_event(
      payload, sig_header, endpoint_secret
    )
  except ValueError as e:
    # Invalid payload
    print('Error parsing payload: {}'.format(str(e)))
    return HttpResponse(status=400)
  except stripe.error.SignatureVerificationError as e:
    # Invalid signature
    print('Error verifying webhook signature: {}'.format(str(e)))
    return HttpResponse(status=400)

  # Handle the event
  if event.type == 'payment_intent.succeeded':
    payment_intent = event.data.object # contains a stripe.PaymentIntent
    print('PaymentIntent was successful!')
  elif event.type == 'payment_method.attached':
    payment_method = event.data.object # contains a stripe.PaymentMethod
    print('PaymentMethod was attached to a Customer!')
  # ... handle other event types
  else:
    print('Unhandled event type {}'.format(event.type))
import json

# Webhooks are always sent as HTTP POST requests, so ensure
# that only POST requests reach your webhook view by
# decorating `webhook()` with `require_POST`.
#
# To ensure that the webhook view can receive webhooks,
# also decorate `webhook()` with `csrf_exempt`.
@require_POST
@csrf_exempt
def webhook(request):
import json
from django.http import HttpResponse

# Using Django
@csrf_exempt
def my_webhook_view(request):
  payload = request.body
  event = None

  try:
    event = stripe.Event.construct_from(
      json.loads(payload), stripe.api_key
    )
  except ValueError as e:
    # Invalid payload
    return HttpResponse(status=400)

  # Handle the event
  if event.type == 'payment_intent.succeeded':
    payment_intent = event.data.object # contains a stripe.PaymentIntent
    # Then define and call a method to handle the successful payment intent.
    # handle_payment_intent_succeeded(payment_intent)
  elif event.type == 'payment_method.attached':
    payment_method = event.data.object # contains a stripe.PaymentMethod
    # Then define and call a method to handle the successful attachment of a PaymentMethod.
    # handle_payment_method_attached(payment_method)
  # ... handle other event types
  else:
    print('Unhandled event type {}'.format(event.type))

  return HttpResponse(status=200)
stripe listen --forward-to localhost:4242/stripe_webhooks
stripe listen --events payment_intent.created,customer.created,payment_intent.succeeded,checkout.session.completed,payment_intent.payment_failed \
  --forward-to localhost:4242/webhook
stripe listen --load-from-webhooks-api --forward-to localhost:5000
Ready! Your webhook signing secret is '{{whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS}}' (^C to quit)


stripe trigger payment_intent.succeeded
Running fixture for: payment_intent
Trigger succeeded! Check dashboard for event details.
[
](https://<[your-website](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862>/<we_1Ova66GF83d3fsgW2nbowkDw>)
  # Process webhook data in `request.body`  return HttpResponse(status=200)
# Set your secret key. Remember to switch to your live secret key in production.
# See your keys here: https://dashboard.stripe.com/apikeys
stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'

from django.http import HttpResponse

# If you are testing your webhook locally with the Stripe CLI you
# can find the endpoint's secret by running `stripe listen`
# Otherwise, find your endpoint's secret in your webhook settings in the Developer Dashboard
endpoint_secret = 'whsec_...'

# Using Django
@csrf_exempt
def my_webhook_view(request):
  payload = request.body
  sig_header = request.META['Stripe-Signature:
t=1492774577,
v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd,
v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39']
  event = None

  try:
    event = stripe.Webhook.construct_event(
      payload, sig_header, endpoint_secret
    )
  except ValueError as e:
    # Invalid payload
    print('Error parsing payload: {}'.format(str(e)))
    return HttpResponse(status=400)
  except stripe.error.SignatureVerificationError as e:
    # Invalid signature
    print('Error verifying webhook signature: {}'.format(str(e)))
    return HttpResponse(status=400)

  # Handle the event
  if event.type == 'payment_intent.succeeded':
    payment_intent = event.data.object # contains a stripe.PaymentIntent
    print('PaymentIntent was successful!')
  elif event.type == 'payment_method.attached':
    payment_method = event.data.object # contains a stripe.PaymentMethod
    print('PaymentMethod was attached to a Customer!')
  # ... handle other event types
  else:
    print('Unhandled event type {}'.format(event.type))

  return HttpResponse(status=200)
  import json

# Webhooks are always sent as HTTP POST requests, so ensure
# that only POST requests reach your webhook view by
# decorating `webhook()` with `require_POST`.
#
# To ensure that the webhook view can receive webhooks,
# also decorate `webhook()` with `csrf_exempt`.
@require_POST
@csrf_exempt
def webhook(request):
THE EVENT OBJECT
{
  "id": "evt_1NG8Du2eZvKYlo2CUI79vXWy",
  "object": "event",
  "api_version": "2019-02-19",
  "created": 1686089970,
  "data": {
    "object": {
      "id": "seti_1NG8Du2eZvKYlo2C9XMqbR0x",
      "object": "setup_intent",
      "application": null,
      "automatic_payment_methods": null,
      "cancellation_reason": null,
      "client_secret": "seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ",
      "created": 1686089970,
      "customer": null,
      "description": null,
      "flow_directions": null,
      "last_setup_error": null,
      "latest_attempt": null,
      "livemode": false,
      "mandate": null,
      "metadata": {},
      "next_action": null,
      "on_behalf_of": null,
      "payment_method": "pm_1NG8Du2eZvKYlo2CYzzldNr7",
      "payment_method_options": {
        "acss_debit": {
          "currency": "cad",
          "mandate_options": {
            "interval_description": "First day of every month",
            "payment_schedule": "interval",
            "transaction_type": "personal"
          },
          "verification_method": "automatic"
        }
      },
      "payment_method_types": [
        "acss_debit"
      ],
      "single_use_mandate": null,
      "status": "requires_confirmation",
      "usage": "off_session"
    }
  },
  "livemode": false,
  "pending_webhooks": 0,
  "request": {
    "id": null,
    "idempotency_key": null
  },
  "type": "setup_intent.created"


  # Process webhook data in `request.body`
---
 README.md | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)

diff --git a/README.md b/README.md
index 1f3d7ba..1efe598 100644
--- a/README.md
+++ b/README.md
@@ -248,7 +248,7 @@ stripe trigger payment_intent.succeeded
 Running fixture for: payment_intent
 Trigger succeeded! Check dashboard for event details.
 [
-](https://<[your-website](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862>/<whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS>)
+](https://<[your-website](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862>/<we_1Ova66GF83d3fsgW2nbowkDw>)
   # Process webhook data in `request.body`  return HttpResponse(status=200)
 # Set your secret key. Remember to switch to your live secret key in production.
 # See your keys here: https://dashboard.stripe.com/apikeys
---
 README.md | 383 ++++++++++++++++++++++++++++++++++++++++++++++++++++++
 1 file changed, 383 insertions(+)

diff --git a/README.md b/README.md
index 1efe598..1e08c57 100644
--- a/README.md
+++ b/README.md
@@ -361,3 +361,386 @@ THE EVENT OBJECT
 
 
   # Process webhook data in `request.body`
+
+  PATCH
+
+# AGENCY-WEBHOOK
+
+Download
+#! /usr/bin/env python3.6
+# Python 3.6 or newer required.
+
+import json
+import os
+import stripe
+# This is your test secret API key.
+stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'
+
+# Replace this endpoint secret with your endpoint's unique secret
+# If you are testing with the CLI, find the secret by running 'stripe listen'
+# If you are using an endpoint defined with the API or dashboard, look in your webhook settings
+# at https://dashboard.stripe.com/webhooks
+endpoint_secret = 'whsec_...'
+from flask import Flask, jsonify, request
+
+app = Flask(__name__)
+
+@app.route('/webhook', methods=['POST'])
+def webhook():
+    event = None
+    payload = request.data
+
+    try:
+        event = json.loads(payload)
+    except json.decoder.JSONDecodeError as e:
+        print('⚠️  Webhook error while parsing basic request.' + str(e))
+        return jsonify(success=False)
+    if endpoint_secret:
+        # Only verify the event if there is an endpoint secret defined
+        # Otherwise use the basic event deserialized with json
+        sig_header = request.headers.get('stripe-signature')
+        try:
+            event = stripe.Webhook.construct_event(
+                payload, sig_header, endpoint_secret
+            )
+        except stripe.error.SignatureVerificationError as e:
+            print('⚠️  Webhook signature verification failed.' + str(e))
+            return jsonify(success=False)
+
+    # Handle the event
+    if event and event['type'] == 'payment_intent.succeeded':
+        payment_intent = event['data']['object']  # contains a stripe.PaymentIntent
+        print('Payment for {} succeeded'.format(payment_intent['amount']))
+        # Then define and call a method to handle the successful payment intent.
+        # handle_payment_intent_succeeded(payment_intent)
+    elif event['type'] == 'payment_method.attached':
+        payment_method = event['data']['object']  # contains a stripe.PaymentMethod
+        # Then define and call a method to handle the successful attachment of a PaymentMethod.
+        # handle_payment_method_attached(payment_method)
+    else:
+        # Unexpected event type
+        print('Unhandled event type {}'.format(event['type']))
+
+    return jsonify(success=True)
+[
+](https://github.com/grateful345/AGENCY-WEBHOOK.git)https://github.com/grateful345/AGENCY-WEBHOOK.git
+echo "# AGENCY-WEBHOOK" >> README.md
+git init
+git add README.md
+git commit -m "first commit"
+git branch -M main
+git remote add origin https://github.com/grateful345/AGENCY-WEBHOOK.git
+git push -u origin main
+…or push an existing repository from the command line
+git remote add origin https://github.com/grateful345/AGENCY-WEBHOOK.git
+git branch -M main
+git push -u origin main
+Install the Stripe Python package
+Install the Stripe package and import it in your code. Alternatively, if you’re starting from scratch and need a requirements.txt file, download the project files using the link in the code editor.
+
+pip
+
+GitHub
+Install the package via pip:
+pip3 install stripe
+
+Server
+Create a new endpoint
+
+settings
+A webhook is an endpoint on your server that receives requests from Stripe, notifying you about events that happen on your account such as a customer disputing a charge or a successful recurring payment. Add a new endpoint to your server and make sure it’s publicly accessible so we can send unauthenticated POST requests.
+Server
+2
+Handle requests from Stripe
+Read the event data
+Stripe sends the event data in the request body. Each event is structured as an Event object with a type, id, and related Stripe resource nested under data.
+Server
+Handle the event
+As soon as you have the event object, check the type to know what kind of event happened. You can use one webhook to handle several different event types at once, or set up individual endpoints for specific events.
+Server
+Return a 200 response
+Build and run your server to test the endpoint at http://localhost:4242/webhook.
+python3 -m flask run --port=4242
+
+Server
+Download the CLI
+Use the Stripe CLI to test your webhook locally. Download the CLI and log in with your Stripe account. Alternatively, use a service like ngrok to make your local endpoint publicly accessible.
+stripe login
+
+Run in the Stripe Shell
+Server
+Forward events to your webhook
+
+settings
+Set up event forwarding with the CLI to send all Stripe events in testmode to your local webhook endpoint.
+stripe listen --forward-to localhost:4242/webhook
+
+Run in the Stripe Shell
+Server
+Simulate events
+
+settings
+Use the CLI to simulate specific events that test your webhook application logic by sending a POST request to your webhook endpoint with a mocked Stripe event object.
+stripe trigger payment_intent.succeeded
+
+Run in the Stripe Shell
+Server
+Congratulations!
+Stripe-Signature:
+t=1492774577,
+v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd,
+v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39
+
+You have a basic webhook endpoint ready to accept events from Stripe. Now add the application logic that your business needs to handle the events you care the most about. You can also extend your endpoint with the steps b
+[
+](https://<your-website>/<your-webhook-endpoint>)https://<your-website>/<[webhook](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862-endpoint>
+README.md | 3 +++
+1 file changed, 3 insertions(+)
+
+diff --git a/README.md b/README.md
+index 806cda8..9b1de77 100644
+--- a/README.md
++++ b/README.md
+@@ -121,3 +121,6 @@ Run in the Stripe Shell
+Server
+Congratulations!
+You have a basic webhook endpoint ready to accept events from Stripe. Now add the application logic that your business needs to handle the events you care the most about. You can also extend your endpoint with the steps b
++
++https:///<webhookhttps://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862-endpoint>
+# Set your secret key. Remember to switch to your live secret key in production.
+# See your keys here: https://dashboard.stripe.com/apikeys
+stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'
+
+endpoint = stripe.WebhookEndpoint.create(
+  url='https://example.com/my/webhook/endpoint',
+  enabled_events=[
+    'payment_intent.payment_failed',
+    'payment_intent.succeeded',
+  ],
+)
+# Set your secret key. Remember to switch to your live secret key in production.
+# See your keys here: https://dashboard.stripe.com/apikeys
+stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'
+
+from django.http import HttpResponse
+
+# If you are testing your webhook locally with the Stripe CLI you
+# can find the endpoint's secret by running `stripe listen`
+# Otherwise, find your endpoint's secret in your webhook settings in the Developer Dashboard
+endpoint_secret = 'whsec_...'
+
+# Using Django
+@csrf_exempt
+def my_webhook_view(request):
+  payload = request.body
+  sig_header = request.META['t=1492774577,
+v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd,
+v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39']
+  event = None
+
+  try:
+    event = stripe.Webhook.construct_event(
+      payload, sig_header, endpoint_secret
+    )
+  except ValueError as e:
+    # Invalid payload
+    print('Error parsing payload: {}'.format(str(e)))
+    return HttpResponse(status=400)
+  except stripe.error.SignatureVerificationError as e:
+    # Invalid signature
+    print('Error verifying webhook signature: {}'.format(str(e)))
+    return HttpResponse(status=400)
+
+  # Handle the event
+  if event.type == 'payment_intent.succeeded':
+    payment_intent = event.data.object # contains a stripe.PaymentIntent
+    print('PaymentIntent was successful!')
+  elif event.type == 'payment_method.attached':
+    payment_method = event.data.object # contains a stripe.PaymentMethod
+    print('PaymentMethod was attached to a Customer!')
+  # ... handle other event types
+  else:
+    print('Unhandled event type {}'.format(event.type))
+import json
+
+# Webhooks are always sent as HTTP POST requests, so ensure
+# that only POST requests reach your webhook view by
+# decorating `webhook()` with `require_POST`.
+#
+# To ensure that the webhook view can receive webhooks,
+# also decorate `webhook()` with `csrf_exempt`.
+@require_POST
+@csrf_exempt
+def webhook(request):
+import json
+from django.http import HttpResponse
+
+# Using Django
+@csrf_exempt
+def my_webhook_view(request):
+  payload = request.body
+  event = None
+
+  try:
+    event = stripe.Event.construct_from(
+      json.loads(payload), stripe.api_key
+    )
+  except ValueError as e:
+    # Invalid payload
+    return HttpResponse(status=400)
+
+  # Handle the event
+  if event.type == 'payment_intent.succeeded':
+    payment_intent = event.data.object # contains a stripe.PaymentIntent
+    # Then define and call a method to handle the successful payment intent.
+    # handle_payment_intent_succeeded(payment_intent)
+  elif event.type == 'payment_method.attached':
+    payment_method = event.data.object # contains a stripe.PaymentMethod
+    # Then define and call a method to handle the successful attachment of a PaymentMethod.
+    # handle_payment_method_attached(payment_method)
+  # ... handle other event types
+  else:
+    print('Unhandled event type {}'.format(event.type))
+
+  return HttpResponse(status=200)
+stripe listen --forward-to localhost:4242/stripe_webhooks
+stripe listen --events payment_intent.created,customer.created,payment_intent.succeeded,checkout.session.completed,payment_intent.payment_failed \
+  --forward-to localhost:4242/webhook
+stripe listen --load-from-webhooks-api --forward-to localhost:5000
+Ready! Your webhook signing secret is '{{whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS}}' (^C to quit)
+
+
+stripe trigger payment_intent.succeeded
+Running fixture for: payment_intent
+Trigger succeeded! Check dashboard for event details.
+[
+](https://<[your-website](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862>/<we_1Ova66GF83d3fsgW2nbowkDw>)
+  # Process webhook data in `request.body`  return HttpResponse(status=200)
+# Set your secret key. Remember to switch to your live secret key in production.
+# See your keys here: https://dashboard.stripe.com/apikeys
+stripe.api_key = 'sk_test_51OR5ePGF83d3fsgWlh41IbGHGtqdiPuFhrcWczglEeFJvQxajyQVCQiZYVZz62HOuYL9tA8dxEQ2MRbxbcYsf8OF00CdDfT6Xq'
+
+from django.http import HttpResponse
+
+# If you are testing your webhook locally with the Stripe CLI you
+# can find the endpoint's secret by running `stripe listen`

$ stripe listen

> Ready! Your webhook signing secret is whsec_abcdefg1234567
2022-01-28 09:47:46   --> customer.created [evt_abc123]
2022-01-28 09:48:22   --> charge.succeeded [evt_def456]
2022-01-28 09:48:58   --> charge.succeeded [evt_ghi789]

stripe listen --forward-to http://localhost:4242

stripe listen --events=payment_intent.succeeded
+# Otherwise, find your endpoint's secret in your webhook settings in the Developer Dashboard
+endpoint_secret = 'whsec_...'
+
+# Using Django
+@csrf_exempt
+def my_webhook_view(request):
+  payload = request.body
+  sig_header = request.META['t=1492774577,
+v1=5257a869e7ecebeda32affa62cdca3fa51cad7e77a0e56ff536d0ce8e108d8bd,
+v0=6ffbb59b2300aae63f272406069a9788598b792a944a07aba816edb039989a39']
+  event = None
+
+  try:
+    event = stripe.Webhook.construct_event(
+      payload, sig_header, endpoint_secret
+    )
+  except ValueError as e:
+    # Invalid payload
+    print('Error parsing payload: {}'.format(str(e)))
+    return HttpResponse(status=400)
+  except stripe.error.SignatureVerificationError as e:
+    # Invalid signature
+    print('Error verifying webhook signature: {}'.format(str(e)))
+    return HttpResponse(status=400)
+
+  # Handle the event
+  if event.type == 'payment_intent.succeeded':
+    payment_intent = event.data.object # contains a stripe.PaymentIntent
+    print('PaymentIntent was successful!')
+  elif event.type == 'payment_method.attached':
+    payment_method = event.data.object # contains a stripe.PaymentMethod
+    print('PaymentMethod was attached to a Customer!')
+  # ... handle other event types
+  else:
+    print('Unhandled event type {}'.format(event.type))
+
+  return HttpResponse(status=200)
+  import json
+
+# Webhooks are always sent as HTTP POST requests, so ensure
+# that only POST requests reach your webhook view by
+# decorating `webhook()` with `require_POST`.
+#
+# To ensure that the webhook view can receive webhooks,
+# also decorate `webhook()` with `csrf_exempt`.
+@require_POST
+@csrf_exempt
+def webhook(request):
+THE EVENT OBJECT
+{
+  "id": "evt_1NG8Du2eZvKYlo2CUI79vXWy",
+  "object": "event",
+  "api_version": "2019-02-19",
+  "created": 1686089970,
+  "data": {
+    "object": {
+      "id": "seti_1NG8Du2eZvKYlo2C9XMqbR0x",
+      "object": "setup_intent",
+      "application": null,
+      "automatic_payment_methods": null,
+      "cancellation_reason": null,
+      "client_secret": "seti_1NG8Du2eZvKYlo2C9XMqbR0x_secret_O2CdhLwGFh2Aej7bCY7qp8jlIuyR8DJ",
+      "created": 1686089970,
+      "customer": null,
+      "description": null,
+      "flow_directions": null,
+      "last_setup_error": null,
+      "latest_attempt": null,
+      "livemode": false,
+      "mandate": null,
+      "metadata": {},
+      "next_action": null,
+      "on_behalf_of": null,
+      "payment_method": "pm_1NG8Du2eZvKYlo2CYzzldNr7",
+      "payment_method_options": {
+        "acss_debit": {
+          "currency": "cad",
+          "mandate_options": {
+            "interval_description": "First day of every month",
+            "payment_schedule": "interval",
+            "transaction_type": "personal"
+          },
+          "verification_method": "automatic"
+        }
+      },
+      "payment_method_types": [
+        "acss_debit"
+      ],
+      "single_use_mandate": null,
+      "status": "requires_confirmation",
+      "usage": "off_session"
+    }
+  },
+  "livemode": false,
+  "pending_webhooks": 0,
+  "request": {
+    "id": null,
+    "idempotency_key": null
+  },
+  "type": "setup_intent.created"
+
+
+  # Process webhook data in `request.body`
+---
+ README.md | 2 +-
+ 1 file changed, 1 insertion(+), 1 deletion(-)
+
+diff --git a/README.md b/README.md
+index 1f3d7ba..1efe598 100644
+--- a/README.md
++++ b/README.md
+@@ -248,7 +248,7 @@ stripe trigger payment_intent.succeeded
+ Running fixture for: payment_intent
+ Trigger succeeded! Check dashboard for event details.
+ [
+-](https://<[your-website](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862>/<whsec_ 5V2GHGaht2mGJGNOmesTtTaxuJWFRssS>)
++](https://<[your-website](https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862)https://scpf-foundation-roblox.fandom.com/wiki/The_Administrator?oldid=2862>/<we_1Ova66GF83d3fsgW2nbowkDw>)
+   # Process webhook data in `request.body`  return HttpResponse(status=200)
+ # Set your secret key. Remember to switch to your live secret key in production.
+ # See your keys here: https://dashboard.stripe.com/apikeys
stripe trigger invoice.payment_succeeded

Setting up fixture for: customer
Setting up fixture for: invoiceitem
Setting up fixture for: invoice
Setting up fixture for: invoice_pay
Trigger succeeded! Check dashboard for event details.

stripe trigger --help

Supported events:
  balance.available
  charge.captured
  charge.dispute.created
  charge.failed
  charge.refunded
  charge.succeeded
...
{
  "object": {
    "id": "file_1OvyoVGF83d3fsgWJ2y8LUzQ",
    "object": "file",
    "created": 1710839911,
    "expires_at": null,
    "filename": "Untitled_20240318.csv",
    "links": {
      "object": "list",
      "data": [],
      "has_more": false,
      "url": "/v1/file_links?file=file_1OvyoVGF83d3fsgWJ2y8LUzQ"
    },
    "purpose": "sigma_scheduled_query",
    "size": 64,
    "title": "Untitled for 2024-03-18",
    "type": "csv",
    "url": "https://files.stripe.com/v1/files/file_1OvyoVGF83d3fsgWJ2y8LUzQ/contents"
  },
  "previous_attributes": null
}



