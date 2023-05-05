How to install istio ?
======================

1. Install istioctl binary from the official website

2. Install the istio by following command

istioctl install --set profile=demo -y

3. Verify the installation by running the following command.

istioctl verify-install

4. Now, we need to inject the istio envoy to the namespace which we are about to deploy the application. Use the following command to inject it. 

kubectl label namespace default istio-injection=enabled 

5. Install kiali dashboard by downloading the latest istio release and apply all the files in the addons folder. This step is not mandatory to proceed to the next steps

Deploying the application
=========================

Note1: This application deploys in the default namespace

Note2: This application has custom domain. If you don't have custom domain replace "*" instead of custom domain. If you have custom domain only you can able to route to the multiple application. If you don't have custom domain install only one application.

1. Deploy the applications by going to the Application folder.

2. Deploy the Istioconfiguration by going to the IstioConfiguration folder

3. if you need to configure SSL to the application. Generate one by reading the readme.md in SSL_Certificate folder.

4. After completing step3, apply the istioConfiguration with SSL.



