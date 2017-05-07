# Getting started

## How to Build

The generated code has dependencies over external libraries like UniRest. These dependencies are defined in the ```composer.json``` file that comes with the SDK. 
To resolve these dependencies, we use the Composer package manager which requires PHP greater than 5.3.2 installed in your system. 
Visit [https://getcomposer.org/download/](https://getcomposer.org/download/) to download the installer file for Composer and run it in your system. 
Open command prompt and type ```composer --version```. This should display the current version of the Composer installed if the installation was successful.

* Using command line, navigate to the directory containing the generated files (including ```composer.json```) for the SDK. 
* Run the command ```composer install```. This should install all the required dependencies and create the ```vendor``` directory in your project directory.

![Building SDK - Step 1](https://apidocs.io/illustration/php?step=installDependencies&workspaceFolder=Kubernetes-PHP)

### [For Windows Users Only] Configuring CURL Certificate Path in php.ini

CURL used to include a list of accepted CAs, but no longer bundles ANY CA certs. So by default it will reject all SSL certificates as unverifiable. You will have to get your CA's cert and point curl at it. The steps are as follows:

1. Download the certificate bundle (.pem file) from [https://curl.haxx.se/docs/caextract.html](https://curl.haxx.se/docs/caextract.html) on to your system.
2. Add curl.cainfo = "PATH_TO/cacert.pem" to your php.ini file located in your php installation. “PATH_TO” must be an absolute path containing the .pem file.

```ini
[curl]
; A default value for the CURLOPT_CAINFO option. This is required to be an
; absolute path.
;curl.cainfo =
```

## How to Use

The following section explains how to use the KubernetesLib library in a new project.

### 1. Open Project in an IDE

Open an IDE for PHP like PhpStorm. The basic workflow presented here is also applicable if you prefer using a different editor or IDE.

![Open project in PHPStorm - Step 1](https://apidocs.io/illustration/php?step=openIDE&workspaceFolder=Kubernetes-PHP)

Click on ```Open``` in PhpStorm to browse to your generated SDK directory and then click ```OK```.

![Open project in PHPStorm - Step 2](https://apidocs.io/illustration/php?step=openProject0&workspaceFolder=Kubernetes-PHP)     

### 2. Add a new Test Project

Create a new directory by right clicking on the solution name as shown below:

![Add a new project in PHPStorm - Step 1](https://apidocs.io/illustration/php?step=createDirectory&workspaceFolder=Kubernetes-PHP)

Name the directory as "test"

![Add a new project in PHPStorm - Step 2](https://apidocs.io/illustration/php?step=nameDirectory&workspaceFolder=Kubernetes-PHP)
   
Add a PHP file to this project

![Add a new project in PHPStorm - Step 3](https://apidocs.io/illustration/php?step=createFile&workspaceFolder=Kubernetes-PHP)

Name it "testSDK"

![Add a new project in PHPStorm - Step 4](https://apidocs.io/illustration/php?step=nameFile&workspaceFolder=Kubernetes-PHP)

Depending on your project setup, you might need to include composer's autoloader in your PHP code to enable auto loading of classes.

```PHP
require_once "../vendor/autoload.php";
```

It is important that the path inside require_once correctly points to the file ```autoload.php``` inside the vendor directory created during dependency installations.

![Add a new project in PHPStorm - Step 4](https://apidocs.io/illustration/php?step=projectFiles&workspaceFolder=Kubernetes-PHP)

After this you can add code to initialize the client library and acquire the instance of a Controller class. Sample code to initialize the client library and using controller methods is given in the subsequent sections.

### 3. Run the Test Project

To run your project you must set the Interpreter for your project. Interpreter is the PHP engine installed on your computer.

Open ```Settings``` from ```File``` menu.

![Run Test Project - Step 1](https://apidocs.io/illustration/php?step=openSettings&workspaceFolder=Kubernetes-PHP)

Select ```PHP``` from within ```Languages & Frameworks```

![Run Test Project - Step 2](https://apidocs.io/illustration/php?step=setInterpreter0&workspaceFolder=Kubernetes-PHP)

Browse for Interpreters near the ```Interpreter``` option and choose your interpreter.

![Run Test Project - Step 3](https://apidocs.io/illustration/php?step=setInterpreter1&workspaceFolder=Kubernetes-PHP)

Once the interpreter is selected, click ```OK```

![Run Test Project - Step 4](https://apidocs.io/illustration/php?step=setInterpreter2&workspaceFolder=Kubernetes-PHP)

To run your project, right click on your PHP file inside your Test project and click on ```Run```

![Run Test Project - Step 5](https://apidocs.io/illustration/php?step=runProject&workspaceFolder=Kubernetes-PHP)

## How to Test

Unit tests in this SDK can be run using PHPUnit. 

1. First install the dependencies using composer including the `require-dev` dependencies.
2. Run `vendor\bin\phpunit --verbose` from commandline to execute tests. If you have 
   installed PHPUnit globally, run tests using `phpunit --verbose` instead.

You can change the PHPUnit test configuration in the `phpunit.xml` file.

## Initialization

### Authentication
In order to setup authentication and initialization of the API client, you need the following information.

| Parameter | Description |
|-----------|-------------|
| authorization | Bearer Token authentication |



API client can be initialized as following.

```php
// Configuration parameters and credentials
$authorization = "authorization"; // Bearer Token authentication

$client = new KubernetesLib\KubernetesLibClient($authorization);
```

# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [CoreController](#core_controller)
* [CoreV1Controller](#core_v1_controller)
* [ApisController](#apis_controller)
* [AppsController](#apps_controller)
* [AppsV1beta1Controller](#apps_v1beta1_controller)
* [AuthenticationController](#authentication_controller)
* [AuthenticationV1Controller](#authentication_v1_controller)
* [AuthenticationV1beta1Controller](#authentication_v1beta1_controller)
* [AuthorizationController](#authorization_controller)
* [AuthorizationV1Controller](#authorization_v1_controller)
* [AuthorizationV1beta1Controller](#authorization_v1beta1_controller)
* [AutoscalingController](#autoscaling_controller)
* [AutoscalingV1Controller](#autoscaling_v1_controller)
* [AutoscalingV2alpha1Controller](#autoscaling_v2alpha1_controller)
* [BatchController](#batch_controller)
* [BatchV1Controller](#batch_v1_controller)
* [BatchV2alpha1Controller](#batch_v2alpha1_controller)
* [CertificatesController](#certificates_controller)
* [CertificatesV1beta1Controller](#certificates_v1beta1_controller)
* [ExtensionsController](#extensions_controller)
* [ExtensionsV1beta1Controller](#extensions_v1beta1_controller)
* [PolicyController](#policy_controller)
* [PolicyV1beta1Controller](#policy_v1beta1_controller)
* [RbacAuthorizationController](#rbac_authorization_controller)
* [RbacAuthorizationV1alpha1Controller](#rbac_authorization_v1alpha1_controller)
* [RbacAuthorizationV1beta1Controller](#rbac_authorization_v1beta1_controller)
* [SettingsController](#settings_controller)
* [SettingsV1alpha1Controller](#settings_v1alpha1_controller)
* [StorageController](#storage_controller)
* [StorageV1Controller](#storage_v1_controller)
* [StorageV1beta1Controller](#storage_v1beta1_controller)
* [LogsController](#logs_controller)
* [VersionController](#version_controller)

## <a name="core_controller"></a>![Class: ](https://apidocs.io/img/class.png ".CoreController") CoreController

### Get singleton instance

The singleton instance of the ``` CoreController ``` class can be accessed from the API Client.

```php
$core = $client->getCore();
```

### <a name="get_core_api_versions"></a>![Method: ](https://apidocs.io/img/method.png ".CoreController.getCoreAPIVersions") getCoreAPIVersions

> get available API versions


```php
function getCoreAPIVersions()
```

#### Example Usage

```php

$result = $core->getCoreAPIVersions();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="core_v1_controller"></a>![Class: ](https://apidocs.io/img/class.png ".CoreV1Controller") CoreV1Controller

### Get singleton instance

The singleton instance of the ``` CoreV1Controller ``` class can be accessed from the API Client.

```php
$coreV1 = $client->getCoreV1();
```

### <a name="get_core_v1_api_resources"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getCoreV1APIResources") getCoreV1APIResources

> get available resources


```php
function getCoreV1APIResources()
```

#### Example Usage

```php

$result = $coreV1->getCoreV1APIResources();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_component_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1ComponentStatus") listCoreV1ComponentStatus

> list objects of kind ComponentStatus


```php
function listCoreV1ComponentStatus(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 229;
$watch = true;

$result = $coreV1->listCoreV1ComponentStatus($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_component_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1ComponentStatus") getReadCoreV1ComponentStatus

> read the specified ComponentStatus


```php
function getReadCoreV1ComponentStatus(
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ComponentStatus |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$pretty = 'pretty';

$result = $coreV1->getReadCoreV1ComponentStatus($name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_config_map_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1ConfigMapForAllNamespaces") listCoreV1ConfigMapForAllNamespaces

> list or watch objects of kind ConfigMap


```php
function listCoreV1ConfigMapForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 229;
$watch = true;

$result = $coreV1->listCoreV1ConfigMapForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_endpoints_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1EndpointsForAllNamespaces") listCoreV1EndpointsForAllNamespaces

> list or watch objects of kind Endpoints


```php
function listCoreV1EndpointsForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 229;
$watch = true;

$result = $coreV1->listCoreV1EndpointsForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_event_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1EventForAllNamespaces") listCoreV1EventForAllNamespaces

> list or watch objects of kind Event


```php
function listCoreV1EventForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 229;
$watch = true;

$result = $coreV1->listCoreV1EventForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_limit_range_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1LimitRangeForAllNamespaces") listCoreV1LimitRangeForAllNamespaces

> list or watch objects of kind LimitRange


```php
function listCoreV1LimitRangeForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 229;
$watch = true;

$result = $coreV1->listCoreV1LimitRangeForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_namespace"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1Namespace") listCoreV1Namespace

> list or watch objects of kind Namespace


```php
function listCoreV1Namespace(
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 229;
$watch = true;
$pretty = 'pretty';

$result = $coreV1->listCoreV1Namespace($fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_core_v1_namespace"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createCoreV1Namespace") createCoreV1Namespace

> create a Namespace


```php
function createCoreV1Namespace(
        $body,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1Namespace();
$pretty = 'pretty';

$result = $coreV1->createCoreV1Namespace($body, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_collection_namespace"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1CollectionNamespace") deleteCoreV1CollectionNamespace

> delete collection of Namespace


```php
function deleteCoreV1CollectionNamespace(
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 229;
$watch = true;
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1CollectionNamespace($fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_core_v1_namespaced_binding"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createCoreV1NamespacedBinding") createCoreV1NamespacedBinding

> create a Binding


```php
function createCoreV1NamespacedBinding(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1Binding();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->createCoreV1NamespacedBinding($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_namespaced_config_map"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1NamespacedConfigMap") listCoreV1NamespacedConfigMap

> list or watch objects of kind ConfigMap


```php
function listCoreV1NamespacedConfigMap(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 229;
$watch = true;
$pretty = 'pretty';

$result = $coreV1->listCoreV1NamespacedConfigMap($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_core_v1_namespaced_config_map"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createCoreV1NamespacedConfigMap") createCoreV1NamespacedConfigMap

> create a ConfigMap


```php
function createCoreV1NamespacedConfigMap(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1ConfigMap();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->createCoreV1NamespacedConfigMap($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_collection_namespaced_config_map"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1CollectionNamespacedConfigMap") deleteCoreV1CollectionNamespacedConfigMap

> delete collection of ConfigMap


```php
function deleteCoreV1CollectionNamespacedConfigMap(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 65;
$watch = false;
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1CollectionNamespacedConfigMap($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_namespaced_config_map"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1NamespacedConfigMap") getReadCoreV1NamespacedConfigMap

> read the specified ConfigMap


```php
function getReadCoreV1NamespacedConfigMap(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ConfigMap |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = false;
$export = false;
$pretty = 'pretty';

$result = $coreV1->getReadCoreV1NamespacedConfigMap($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_core_v1_namespaced_config_map"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateReplaceCoreV1NamespacedConfigMap") updateReplaceCoreV1NamespacedConfigMap

> replace the specified ConfigMap


```php
function updateReplaceCoreV1NamespacedConfigMap(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ConfigMap |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1ConfigMap();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->updateReplaceCoreV1NamespacedConfigMap($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_namespaced_config_map"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1NamespacedConfigMap") deleteCoreV1NamespacedConfigMap

> delete a ConfigMap


```php
function deleteCoreV1NamespacedConfigMap(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ConfigMap |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 65;
$orphanDependents = false;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1NamespacedConfigMap($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_core_v1_namespaced_config_map"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.patchCoreV1NamespacedConfigMap") patchCoreV1NamespacedConfigMap

> partially update the specified ConfigMap


```php
function patchCoreV1NamespacedConfigMap(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ConfigMap |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->patchCoreV1NamespacedConfigMap($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_namespaced_endpoints"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1NamespacedEndpoints") listCoreV1NamespacedEndpoints

> list or watch objects of kind Endpoints


```php
function listCoreV1NamespacedEndpoints(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 65;
$watch = false;
$pretty = 'pretty';

$result = $coreV1->listCoreV1NamespacedEndpoints($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_core_v1_namespaced_endpoints"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createCoreV1NamespacedEndpoints") createCoreV1NamespacedEndpoints

> create Endpoints


```php
function createCoreV1NamespacedEndpoints(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1Endpoints();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->createCoreV1NamespacedEndpoints($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_collection_namespaced_endpoints"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1CollectionNamespacedEndpoints") deleteCoreV1CollectionNamespacedEndpoints

> delete collection of Endpoints


```php
function deleteCoreV1CollectionNamespacedEndpoints(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 65;
$watch = false;
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1CollectionNamespacedEndpoints($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_namespaced_endpoints"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1NamespacedEndpoints") getReadCoreV1NamespacedEndpoints

> read the specified Endpoints


```php
function getReadCoreV1NamespacedEndpoints(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Endpoints |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = false;
$export = false;
$pretty = 'pretty';

$result = $coreV1->getReadCoreV1NamespacedEndpoints($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_core_v1_namespaced_endpoints"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateReplaceCoreV1NamespacedEndpoints") updateReplaceCoreV1NamespacedEndpoints

> replace the specified Endpoints


```php
function updateReplaceCoreV1NamespacedEndpoints(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Endpoints |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1Endpoints();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->updateReplaceCoreV1NamespacedEndpoints($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_namespaced_endpoints"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1NamespacedEndpoints") deleteCoreV1NamespacedEndpoints

> delete Endpoints


```php
function deleteCoreV1NamespacedEndpoints(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Endpoints |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 65;
$orphanDependents = false;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1NamespacedEndpoints($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_core_v1_namespaced_endpoints"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.patchCoreV1NamespacedEndpoints") patchCoreV1NamespacedEndpoints

> partially update the specified Endpoints


```php
function patchCoreV1NamespacedEndpoints(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Endpoints |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->patchCoreV1NamespacedEndpoints($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_namespaced_event"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1NamespacedEvent") listCoreV1NamespacedEvent

> list or watch objects of kind Event


```php
function listCoreV1NamespacedEvent(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 65;
$watch = false;
$pretty = 'pretty';

$result = $coreV1->listCoreV1NamespacedEvent($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_core_v1_namespaced_event"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createCoreV1NamespacedEvent") createCoreV1NamespacedEvent

> create an Event


```php
function createCoreV1NamespacedEvent(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1Event();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->createCoreV1NamespacedEvent($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_collection_namespaced_event"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1CollectionNamespacedEvent") deleteCoreV1CollectionNamespacedEvent

> delete collection of Event


```php
function deleteCoreV1CollectionNamespacedEvent(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 24;
$watch = false;
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1CollectionNamespacedEvent($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_namespaced_event"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1NamespacedEvent") getReadCoreV1NamespacedEvent

> read the specified Event


```php
function getReadCoreV1NamespacedEvent(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Event |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = false;
$export = false;
$pretty = 'pretty';

$result = $coreV1->getReadCoreV1NamespacedEvent($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_core_v1_namespaced_event"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateReplaceCoreV1NamespacedEvent") updateReplaceCoreV1NamespacedEvent

> replace the specified Event


```php
function updateReplaceCoreV1NamespacedEvent(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Event |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1Event();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->updateReplaceCoreV1NamespacedEvent($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_namespaced_event"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1NamespacedEvent") deleteCoreV1NamespacedEvent

> delete an Event


```php
function deleteCoreV1NamespacedEvent(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Event |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 24;
$orphanDependents = false;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1NamespacedEvent($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_core_v1_namespaced_event"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.patchCoreV1NamespacedEvent") patchCoreV1NamespacedEvent

> partially update the specified Event


```php
function patchCoreV1NamespacedEvent(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Event |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->patchCoreV1NamespacedEvent($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_namespaced_limit_range"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1NamespacedLimitRange") listCoreV1NamespacedLimitRange

> list or watch objects of kind LimitRange


```php
function listCoreV1NamespacedLimitRange(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 24;
$watch = false;
$pretty = 'pretty';

$result = $coreV1->listCoreV1NamespacedLimitRange($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_core_v1_namespaced_limit_range"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createCoreV1NamespacedLimitRange") createCoreV1NamespacedLimitRange

> create a LimitRange


```php
function createCoreV1NamespacedLimitRange(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1LimitRange();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->createCoreV1NamespacedLimitRange($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_collection_namespaced_limit_range"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1CollectionNamespacedLimitRange") deleteCoreV1CollectionNamespacedLimitRange

> delete collection of LimitRange


```php
function deleteCoreV1CollectionNamespacedLimitRange(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 24;
$watch = false;
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1CollectionNamespacedLimitRange($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_namespaced_limit_range"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1NamespacedLimitRange") getReadCoreV1NamespacedLimitRange

> read the specified LimitRange


```php
function getReadCoreV1NamespacedLimitRange(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the LimitRange |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = false;
$export = false;
$pretty = 'pretty';

$result = $coreV1->getReadCoreV1NamespacedLimitRange($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_core_v1_namespaced_limit_range"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateReplaceCoreV1NamespacedLimitRange") updateReplaceCoreV1NamespacedLimitRange

> replace the specified LimitRange


```php
function updateReplaceCoreV1NamespacedLimitRange(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the LimitRange |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1LimitRange();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->updateReplaceCoreV1NamespacedLimitRange($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_namespaced_limit_range"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1NamespacedLimitRange") deleteCoreV1NamespacedLimitRange

> delete a LimitRange


```php
function deleteCoreV1NamespacedLimitRange(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the LimitRange |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 115;
$orphanDependents = false;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1NamespacedLimitRange($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_core_v1_namespaced_limit_range"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.patchCoreV1NamespacedLimitRange") patchCoreV1NamespacedLimitRange

> partially update the specified LimitRange


```php
function patchCoreV1NamespacedLimitRange(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the LimitRange |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->patchCoreV1NamespacedLimitRange($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_namespaced_persistent_volume_claim"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1NamespacedPersistentVolumeClaim") listCoreV1NamespacedPersistentVolumeClaim

> list or watch objects of kind PersistentVolumeClaim


```php
function listCoreV1NamespacedPersistentVolumeClaim(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 115;
$watch = false;
$pretty = 'pretty';

$result = $coreV1->listCoreV1NamespacedPersistentVolumeClaim($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_core_v1_namespaced_persistent_volume_claim"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createCoreV1NamespacedPersistentVolumeClaim") createCoreV1NamespacedPersistentVolumeClaim

> create a PersistentVolumeClaim


```php
function createCoreV1NamespacedPersistentVolumeClaim(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1PersistentVolumeClaim();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->createCoreV1NamespacedPersistentVolumeClaim($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_collection_namespaced_persistent_volume_claim"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1CollectionNamespacedPersistentVolumeClaim") deleteCoreV1CollectionNamespacedPersistentVolumeClaim

> delete collection of PersistentVolumeClaim


```php
function deleteCoreV1CollectionNamespacedPersistentVolumeClaim(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 115;
$watch = false;
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1CollectionNamespacedPersistentVolumeClaim($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_namespaced_persistent_volume_claim"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1NamespacedPersistentVolumeClaim") getReadCoreV1NamespacedPersistentVolumeClaim

> read the specified PersistentVolumeClaim


```php
function getReadCoreV1NamespacedPersistentVolumeClaim(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the PersistentVolumeClaim |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = false;
$export = false;
$pretty = 'pretty';

$result = $coreV1->getReadCoreV1NamespacedPersistentVolumeClaim($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_core_v1_namespaced_persistent_volume_claim"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateReplaceCoreV1NamespacedPersistentVolumeClaim") updateReplaceCoreV1NamespacedPersistentVolumeClaim

> replace the specified PersistentVolumeClaim


```php
function updateReplaceCoreV1NamespacedPersistentVolumeClaim(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the PersistentVolumeClaim |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1PersistentVolumeClaim();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->updateReplaceCoreV1NamespacedPersistentVolumeClaim($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_namespaced_persistent_volume_claim"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1NamespacedPersistentVolumeClaim") deleteCoreV1NamespacedPersistentVolumeClaim

> delete a PersistentVolumeClaim


```php
function deleteCoreV1NamespacedPersistentVolumeClaim(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the PersistentVolumeClaim |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 115;
$orphanDependents = false;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1NamespacedPersistentVolumeClaim($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_core_v1_namespaced_persistent_volume_claim"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.patchCoreV1NamespacedPersistentVolumeClaim") patchCoreV1NamespacedPersistentVolumeClaim

> partially update the specified PersistentVolumeClaim


```php
function patchCoreV1NamespacedPersistentVolumeClaim(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the PersistentVolumeClaim |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->patchCoreV1NamespacedPersistentVolumeClaim($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_namespaced_persistent_volume_claim_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1NamespacedPersistentVolumeClaimStatus") getReadCoreV1NamespacedPersistentVolumeClaimStatus

> read status of the specified PersistentVolumeClaim


```php
function getReadCoreV1NamespacedPersistentVolumeClaimStatus(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the PersistentVolumeClaim |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->getReadCoreV1NamespacedPersistentVolumeClaimStatus($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_core_v1_namespaced_persistent_volume_claim_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateReplaceCoreV1NamespacedPersistentVolumeClaimStatus") updateReplaceCoreV1NamespacedPersistentVolumeClaimStatus

> replace status of the specified PersistentVolumeClaim


```php
function updateReplaceCoreV1NamespacedPersistentVolumeClaimStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the PersistentVolumeClaim |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1PersistentVolumeClaim();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->updateReplaceCoreV1NamespacedPersistentVolumeClaimStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_core_v1_namespaced_persistent_volume_claim_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.patchCoreV1NamespacedPersistentVolumeClaimStatus") patchCoreV1NamespacedPersistentVolumeClaimStatus

> partially update status of the specified PersistentVolumeClaim


```php
function patchCoreV1NamespacedPersistentVolumeClaimStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the PersistentVolumeClaim |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->patchCoreV1NamespacedPersistentVolumeClaimStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_namespaced_pod"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1NamespacedPod") listCoreV1NamespacedPod

> list or watch objects of kind Pod


```php
function listCoreV1NamespacedPod(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 207;
$watch = true;
$pretty = 'pretty';

$result = $coreV1->listCoreV1NamespacedPod($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_core_v1_namespaced_pod"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createCoreV1NamespacedPod") createCoreV1NamespacedPod

> create a Pod


```php
function createCoreV1NamespacedPod(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1Pod();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->createCoreV1NamespacedPod($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_collection_namespaced_pod"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1CollectionNamespacedPod") deleteCoreV1CollectionNamespacedPod

> delete collection of Pod


```php
function deleteCoreV1CollectionNamespacedPod(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 207;
$watch = true;
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1CollectionNamespacedPod($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_namespaced_pod"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1NamespacedPod") getReadCoreV1NamespacedPod

> read the specified Pod


```php
function getReadCoreV1NamespacedPod(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = true;
$export = true;
$pretty = 'pretty';

$result = $coreV1->getReadCoreV1NamespacedPod($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_core_v1_namespaced_pod"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateReplaceCoreV1NamespacedPod") updateReplaceCoreV1NamespacedPod

> replace the specified Pod


```php
function updateReplaceCoreV1NamespacedPod(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1Pod();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->updateReplaceCoreV1NamespacedPod($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_namespaced_pod"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1NamespacedPod") deleteCoreV1NamespacedPod

> delete a Pod


```php
function deleteCoreV1NamespacedPod(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 207;
$orphanDependents = true;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1NamespacedPod($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_core_v1_namespaced_pod"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.patchCoreV1NamespacedPod") patchCoreV1NamespacedPod

> partially update the specified Pod


```php
function patchCoreV1NamespacedPod(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->patchCoreV1NamespacedPod($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_connect_core_v1_get_namespaced_pod_attach"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getConnectCoreV1GetNamespacedPodAttach") getConnectCoreV1GetNamespacedPodAttach

> connect GET requests to attach of Pod


```php
function getConnectCoreV1GetNamespacedPodAttach(
        $name,
        $mnamespace,
        $container = null,
        $stderr = null,
        $stdin = null,
        $stdout = null,
        $tty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| container |  ``` Optional ```  | The container in which to execute the command. Defaults to only container if there is only one container in the pod. |
| stderr |  ``` Optional ```  | Stderr if true indicates that stderr is to be redirected for the attach call. Defaults to true. |
| stdin |  ``` Optional ```  | Stdin if true, redirects the standard input stream of the pod for this call. Defaults to false. |
| stdout |  ``` Optional ```  | Stdout if true indicates that stdout is to be redirected for the attach call. Defaults to true. |
| tty |  ``` Optional ```  | TTY if true indicates that a tty will be allocated for the attach call. This is passed through the container runtime so the tty is allocated on the worker node by the container runtime. Defaults to false. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$container = 'container';
$stderr = true;
$stdin = true;
$stdout = true;
$tty = true;

$result = $coreV1->getConnectCoreV1GetNamespacedPodAttach($name, $mnamespace, $container, $stderr, $stdin, $stdout, $tty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_connect_core_v1_post_namespaced_pod_attach"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createConnectCoreV1PostNamespacedPodAttach") createConnectCoreV1PostNamespacedPodAttach

> connect POST requests to attach of Pod


```php
function createConnectCoreV1PostNamespacedPodAttach(
        $name,
        $mnamespace,
        $container = null,
        $stderr = null,
        $stdin = null,
        $stdout = null,
        $tty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| container |  ``` Optional ```  | The container in which to execute the command. Defaults to only container if there is only one container in the pod. |
| stderr |  ``` Optional ```  | Stderr if true indicates that stderr is to be redirected for the attach call. Defaults to true. |
| stdin |  ``` Optional ```  | Stdin if true, redirects the standard input stream of the pod for this call. Defaults to false. |
| stdout |  ``` Optional ```  | Stdout if true indicates that stdout is to be redirected for the attach call. Defaults to true. |
| tty |  ``` Optional ```  | TTY if true indicates that a tty will be allocated for the attach call. This is passed through the container runtime so the tty is allocated on the worker node by the container runtime. Defaults to false. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$container = 'container';
$stderr = true;
$stdin = true;
$stdout = true;
$tty = true;

$result = $coreV1->createConnectCoreV1PostNamespacedPodAttach($name, $mnamespace, $container, $stderr, $stdin, $stdout, $tty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_core_v1_namespaced_binding_binding"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createCoreV1NamespacedBindingBinding") createCoreV1NamespacedBindingBinding

> create binding of a Binding


```php
function createCoreV1NamespacedBindingBinding(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Binding |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1Binding();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->createCoreV1NamespacedBindingBinding($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_core_v1_namespaced_eviction_eviction"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createCoreV1NamespacedEvictionEviction") createCoreV1NamespacedEvictionEviction

> create eviction of an Eviction


```php
function createCoreV1NamespacedEvictionEviction(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Eviction |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisPolicyV1beta1Eviction();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->createCoreV1NamespacedEvictionEviction($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_connect_core_v1_get_namespaced_pod_exec"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getConnectCoreV1GetNamespacedPodExec") getConnectCoreV1GetNamespacedPodExec

> connect GET requests to exec of Pod


```php
function getConnectCoreV1GetNamespacedPodExec(
        $name,
        $mnamespace,
        $command = null,
        $container = null,
        $stderr = null,
        $stdin = null,
        $stdout = null,
        $tty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| command |  ``` Optional ```  | Command is the remote command to execute. argv array. Not executed within a shell. |
| container |  ``` Optional ```  | Container in which to execute the command. Defaults to only container if there is only one container in the pod. |
| stderr |  ``` Optional ```  | Redirect the standard error stream of the pod for this call. Defaults to true. |
| stdin |  ``` Optional ```  | Redirect the standard input stream of the pod for this call. Defaults to false. |
| stdout |  ``` Optional ```  | Redirect the standard output stream of the pod for this call. Defaults to true. |
| tty |  ``` Optional ```  | TTY if true indicates that a tty will be allocated for the exec call. Defaults to false. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$command = 'command';
$container = 'container';
$stderr = true;
$stdin = true;
$stdout = true;
$tty = true;

$result = $coreV1->getConnectCoreV1GetNamespacedPodExec($name, $mnamespace, $command, $container, $stderr, $stdin, $stdout, $tty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_connect_core_v1_post_namespaced_pod_exec"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createConnectCoreV1PostNamespacedPodExec") createConnectCoreV1PostNamespacedPodExec

> connect POST requests to exec of Pod


```php
function createConnectCoreV1PostNamespacedPodExec(
        $name,
        $mnamespace,
        $command = null,
        $container = null,
        $stderr = null,
        $stdin = null,
        $stdout = null,
        $tty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| command |  ``` Optional ```  | Command is the remote command to execute. argv array. Not executed within a shell. |
| container |  ``` Optional ```  | Container in which to execute the command. Defaults to only container if there is only one container in the pod. |
| stderr |  ``` Optional ```  | Redirect the standard error stream of the pod for this call. Defaults to true. |
| stdin |  ``` Optional ```  | Redirect the standard input stream of the pod for this call. Defaults to false. |
| stdout |  ``` Optional ```  | Redirect the standard output stream of the pod for this call. Defaults to true. |
| tty |  ``` Optional ```  | TTY if true indicates that a tty will be allocated for the exec call. Defaults to false. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$command = 'command';
$container = 'container';
$stderr = true;
$stdin = true;
$stdout = true;
$tty = true;

$result = $coreV1->createConnectCoreV1PostNamespacedPodExec($name, $mnamespace, $command, $container, $stderr, $stdin, $stdout, $tty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_namespaced_pod_log"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1NamespacedPodLog") getReadCoreV1NamespacedPodLog

> read log of the specified Pod


```php
function getReadCoreV1NamespacedPodLog(
        $name,
        $mnamespace,
        $container = null,
        $follow = null,
        $limitBytes = null,
        $pretty = null,
        $previous = null,
        $sinceSeconds = null,
        $tailLines = null,
        $timestamps = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| container |  ``` Optional ```  | The container for which to stream logs. Defaults to only container if there is one container in the pod. |
| follow |  ``` Optional ```  | Follow the log stream of the pod. Defaults to false. |
| limitBytes |  ``` Optional ```  | If set, the number of bytes to read from the server before terminating the log output. This may not display a complete final line of logging, and may return slightly more or slightly less than the specified limit. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| previous |  ``` Optional ```  | Return previous terminated container logs. Defaults to false. |
| sinceSeconds |  ``` Optional ```  | A relative time in seconds before the current time from which to show logs. If this value precedes the time a pod was started, only logs since the pod start will be returned. If this value is in the future, no logs will be returned. Only one of sinceSeconds or sinceTime may be specified. |
| tailLines |  ``` Optional ```  | If set, the number of lines from the end of the logs to show. If not specified, logs are shown from the creation of the container or sinceSeconds or sinceTime |
| timestamps |  ``` Optional ```  | If true, add an RFC3339 or RFC3339Nano timestamp at the beginning of every line of log output. Defaults to false. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$container = 'container';
$follow = true;
$limitBytes = 165;
$pretty = 'pretty';
$previous = true;
$sinceSeconds = 165;
$tailLines = 165;
$timestamps = true;

$result = $coreV1->getReadCoreV1NamespacedPodLog($name, $mnamespace, $container, $follow, $limitBytes, $pretty, $previous, $sinceSeconds, $tailLines, $timestamps);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_connect_core_v1_get_namespaced_pod_portforward"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getConnectCoreV1GetNamespacedPodPortforward") getConnectCoreV1GetNamespacedPodPortforward

> connect GET requests to portforward of Pod


```php
function getConnectCoreV1GetNamespacedPodPortforward(
        $name,
        $mnamespace,
        $ports = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| ports |  ``` Optional ```  | List of ports to forward Required when using WebSockets |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$ports = 165;

$result = $coreV1->getConnectCoreV1GetNamespacedPodPortforward($name, $mnamespace, $ports);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_connect_core_v1_post_namespaced_pod_portforward"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createConnectCoreV1PostNamespacedPodPortforward") createConnectCoreV1PostNamespacedPodPortforward

> connect POST requests to portforward of Pod


```php
function createConnectCoreV1PostNamespacedPodPortforward(
        $name,
        $mnamespace,
        $ports = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| ports |  ``` Optional ```  | List of ports to forward Required when using WebSockets |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$ports = 165;

$result = $coreV1->createConnectCoreV1PostNamespacedPodPortforward($name, $mnamespace, $ports);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_connect_core_v1_get_namespaced_pod_proxy"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getConnectCoreV1GetNamespacedPodProxy") getConnectCoreV1GetNamespacedPodProxy

> connect GET requests to proxy of Pod


```php
function getConnectCoreV1GetNamespacedPodProxy(
        $name,
        $mnamespace,
        $path = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Optional ```  | Path is the URL path to use for the current proxy request to pod. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->getConnectCoreV1GetNamespacedPodProxy($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_connect_core_v1_put_namespaced_pod_proxy"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateConnectCoreV1PutNamespacedPodProxy") updateConnectCoreV1PutNamespacedPodProxy

> connect PUT requests to proxy of Pod


```php
function updateConnectCoreV1PutNamespacedPodProxy(
        $name,
        $mnamespace,
        $path = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Optional ```  | Path is the URL path to use for the current proxy request to pod. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->updateConnectCoreV1PutNamespacedPodProxy($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_connect_core_v1_post_namespaced_pod_proxy"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createConnectCoreV1PostNamespacedPodProxy") createConnectCoreV1PostNamespacedPodProxy

> connect POST requests to proxy of Pod


```php
function createConnectCoreV1PostNamespacedPodProxy(
        $name,
        $mnamespace,
        $path = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Optional ```  | Path is the URL path to use for the current proxy request to pod. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->createConnectCoreV1PostNamespacedPodProxy($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_connect_core_v1_delete_namespaced_pod_proxy"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteConnectCoreV1DeleteNamespacedPodProxy") deleteConnectCoreV1DeleteNamespacedPodProxy

> connect DELETE requests to proxy of Pod


```php
function deleteConnectCoreV1DeleteNamespacedPodProxy(
        $name,
        $mnamespace,
        $path = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Optional ```  | Path is the URL path to use for the current proxy request to pod. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->deleteConnectCoreV1DeleteNamespacedPodProxy($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_connect_core_v1_patch_namespaced_pod_proxy"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateConnectCoreV1PatchNamespacedPodProxy") updateConnectCoreV1PatchNamespacedPodProxy

> connect PATCH requests to proxy of Pod


```php
function updateConnectCoreV1PatchNamespacedPodProxy(
        $name,
        $mnamespace,
        $path = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Optional ```  | Path is the URL path to use for the current proxy request to pod. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->updateConnectCoreV1PatchNamespacedPodProxy($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_connect_core_v1_get_namespaced_pod_proxy_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getConnectCoreV1GetNamespacedPodProxyWithPath") getConnectCoreV1GetNamespacedPodProxyWithPath

> connect GET requests to proxy of Pod


```php
function getConnectCoreV1GetNamespacedPodProxyWithPath(
        $name,
        $mnamespace,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->getConnectCoreV1GetNamespacedPodProxyWithPath($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_connect_core_v1_put_namespaced_pod_proxy_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateConnectCoreV1PutNamespacedPodProxyWithPath") updateConnectCoreV1PutNamespacedPodProxyWithPath

> connect PUT requests to proxy of Pod


```php
function updateConnectCoreV1PutNamespacedPodProxyWithPath(
        $name,
        $mnamespace,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->updateConnectCoreV1PutNamespacedPodProxyWithPath($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_connect_core_v1_post_namespaced_pod_proxy_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createConnectCoreV1PostNamespacedPodProxyWithPath") createConnectCoreV1PostNamespacedPodProxyWithPath

> connect POST requests to proxy of Pod


```php
function createConnectCoreV1PostNamespacedPodProxyWithPath(
        $name,
        $mnamespace,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->createConnectCoreV1PostNamespacedPodProxyWithPath($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_connect_core_v1_delete_namespaced_pod_proxy_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteConnectCoreV1DeleteNamespacedPodProxyWithPath") deleteConnectCoreV1DeleteNamespacedPodProxyWithPath

> connect DELETE requests to proxy of Pod


```php
function deleteConnectCoreV1DeleteNamespacedPodProxyWithPath(
        $name,
        $mnamespace,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->deleteConnectCoreV1DeleteNamespacedPodProxyWithPath($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_connect_core_v1_patch_namespaced_pod_proxy_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateConnectCoreV1PatchNamespacedPodProxyWithPath") updateConnectCoreV1PatchNamespacedPodProxyWithPath

> connect PATCH requests to proxy of Pod


```php
function updateConnectCoreV1PatchNamespacedPodProxyWithPath(
        $name,
        $mnamespace,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->updateConnectCoreV1PatchNamespacedPodProxyWithPath($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_namespaced_pod_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1NamespacedPodStatus") getReadCoreV1NamespacedPodStatus

> read status of the specified Pod


```php
function getReadCoreV1NamespacedPodStatus(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->getReadCoreV1NamespacedPodStatus($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_core_v1_namespaced_pod_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateReplaceCoreV1NamespacedPodStatus") updateReplaceCoreV1NamespacedPodStatus

> replace status of the specified Pod


```php
function updateReplaceCoreV1NamespacedPodStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1Pod();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->updateReplaceCoreV1NamespacedPodStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_core_v1_namespaced_pod_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.patchCoreV1NamespacedPodStatus") patchCoreV1NamespacedPodStatus

> partially update status of the specified Pod


```php
function patchCoreV1NamespacedPodStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->patchCoreV1NamespacedPodStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_namespaced_pod_template"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1NamespacedPodTemplate") listCoreV1NamespacedPodTemplate

> list or watch objects of kind PodTemplate


```php
function listCoreV1NamespacedPodTemplate(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 1;
$watch = false;
$pretty = 'pretty';

$result = $coreV1->listCoreV1NamespacedPodTemplate($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_core_v1_namespaced_pod_template"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createCoreV1NamespacedPodTemplate") createCoreV1NamespacedPodTemplate

> create a PodTemplate


```php
function createCoreV1NamespacedPodTemplate(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1PodTemplate();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->createCoreV1NamespacedPodTemplate($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_collection_namespaced_pod_template"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1CollectionNamespacedPodTemplate") deleteCoreV1CollectionNamespacedPodTemplate

> delete collection of PodTemplate


```php
function deleteCoreV1CollectionNamespacedPodTemplate(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 1;
$watch = false;
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1CollectionNamespacedPodTemplate($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_namespaced_pod_template"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1NamespacedPodTemplate") getReadCoreV1NamespacedPodTemplate

> read the specified PodTemplate


```php
function getReadCoreV1NamespacedPodTemplate(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the PodTemplate |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = false;
$export = false;
$pretty = 'pretty';

$result = $coreV1->getReadCoreV1NamespacedPodTemplate($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_core_v1_namespaced_pod_template"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateReplaceCoreV1NamespacedPodTemplate") updateReplaceCoreV1NamespacedPodTemplate

> replace the specified PodTemplate


```php
function updateReplaceCoreV1NamespacedPodTemplate(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the PodTemplate |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1PodTemplate();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->updateReplaceCoreV1NamespacedPodTemplate($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_namespaced_pod_template"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1NamespacedPodTemplate") deleteCoreV1NamespacedPodTemplate

> delete a PodTemplate


```php
function deleteCoreV1NamespacedPodTemplate(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the PodTemplate |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 1;
$orphanDependents = false;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1NamespacedPodTemplate($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_core_v1_namespaced_pod_template"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.patchCoreV1NamespacedPodTemplate") patchCoreV1NamespacedPodTemplate

> partially update the specified PodTemplate


```php
function patchCoreV1NamespacedPodTemplate(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the PodTemplate |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->patchCoreV1NamespacedPodTemplate($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_namespaced_replication_controller"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1NamespacedReplicationController") listCoreV1NamespacedReplicationController

> list or watch objects of kind ReplicationController


```php
function listCoreV1NamespacedReplicationController(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 1;
$watch = false;
$pretty = 'pretty';

$result = $coreV1->listCoreV1NamespacedReplicationController($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_core_v1_namespaced_replication_controller"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createCoreV1NamespacedReplicationController") createCoreV1NamespacedReplicationController

> create a ReplicationController


```php
function createCoreV1NamespacedReplicationController(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1ReplicationController();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->createCoreV1NamespacedReplicationController($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_collection_namespaced_replication_controller"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1CollectionNamespacedReplicationController") deleteCoreV1CollectionNamespacedReplicationController

> delete collection of ReplicationController


```php
function deleteCoreV1CollectionNamespacedReplicationController(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 1;
$watch = false;
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1CollectionNamespacedReplicationController($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_namespaced_replication_controller"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1NamespacedReplicationController") getReadCoreV1NamespacedReplicationController

> read the specified ReplicationController


```php
function getReadCoreV1NamespacedReplicationController(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ReplicationController |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = false;
$export = false;
$pretty = 'pretty';

$result = $coreV1->getReadCoreV1NamespacedReplicationController($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_core_v1_namespaced_replication_controller"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateReplaceCoreV1NamespacedReplicationController") updateReplaceCoreV1NamespacedReplicationController

> replace the specified ReplicationController


```php
function updateReplaceCoreV1NamespacedReplicationController(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ReplicationController |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1ReplicationController();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->updateReplaceCoreV1NamespacedReplicationController($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_namespaced_replication_controller"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1NamespacedReplicationController") deleteCoreV1NamespacedReplicationController

> delete a ReplicationController


```php
function deleteCoreV1NamespacedReplicationController(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ReplicationController |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 93;
$orphanDependents = false;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1NamespacedReplicationController($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_core_v1_namespaced_replication_controller"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.patchCoreV1NamespacedReplicationController") patchCoreV1NamespacedReplicationController

> partially update the specified ReplicationController


```php
function patchCoreV1NamespacedReplicationController(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ReplicationController |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->patchCoreV1NamespacedReplicationController($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_namespaced_scale_scale"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1NamespacedScaleScale") getReadCoreV1NamespacedScaleScale

> read scale of the specified Scale


```php
function getReadCoreV1NamespacedScaleScale(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Scale |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->getReadCoreV1NamespacedScaleScale($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_core_v1_namespaced_scale_scale"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateReplaceCoreV1NamespacedScaleScale") updateReplaceCoreV1NamespacedScaleScale

> replace scale of the specified Scale


```php
function updateReplaceCoreV1NamespacedScaleScale(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Scale |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAutoscalingV1Scale();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->updateReplaceCoreV1NamespacedScaleScale($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_core_v1_namespaced_scale_scale"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.patchCoreV1NamespacedScaleScale") patchCoreV1NamespacedScaleScale

> partially update scale of the specified Scale


```php
function patchCoreV1NamespacedScaleScale(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Scale |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->patchCoreV1NamespacedScaleScale($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_namespaced_replication_controller_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1NamespacedReplicationControllerStatus") getReadCoreV1NamespacedReplicationControllerStatus

> read status of the specified ReplicationController


```php
function getReadCoreV1NamespacedReplicationControllerStatus(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ReplicationController |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->getReadCoreV1NamespacedReplicationControllerStatus($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_core_v1_namespaced_replication_controller_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateReplaceCoreV1NamespacedReplicationControllerStatus") updateReplaceCoreV1NamespacedReplicationControllerStatus

> replace status of the specified ReplicationController


```php
function updateReplaceCoreV1NamespacedReplicationControllerStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ReplicationController |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1ReplicationController();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->updateReplaceCoreV1NamespacedReplicationControllerStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_core_v1_namespaced_replication_controller_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.patchCoreV1NamespacedReplicationControllerStatus") patchCoreV1NamespacedReplicationControllerStatus

> partially update status of the specified ReplicationController


```php
function patchCoreV1NamespacedReplicationControllerStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ReplicationController |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->patchCoreV1NamespacedReplicationControllerStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_namespaced_resource_quota"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1NamespacedResourceQuota") listCoreV1NamespacedResourceQuota

> list or watch objects of kind ResourceQuota


```php
function listCoreV1NamespacedResourceQuota(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 93;
$watch = false;
$pretty = 'pretty';

$result = $coreV1->listCoreV1NamespacedResourceQuota($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_core_v1_namespaced_resource_quota"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createCoreV1NamespacedResourceQuota") createCoreV1NamespacedResourceQuota

> create a ResourceQuota


```php
function createCoreV1NamespacedResourceQuota(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1ResourceQuota();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->createCoreV1NamespacedResourceQuota($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_collection_namespaced_resource_quota"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1CollectionNamespacedResourceQuota") deleteCoreV1CollectionNamespacedResourceQuota

> delete collection of ResourceQuota


```php
function deleteCoreV1CollectionNamespacedResourceQuota(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 51;
$watch = false;
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1CollectionNamespacedResourceQuota($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_namespaced_resource_quota"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1NamespacedResourceQuota") getReadCoreV1NamespacedResourceQuota

> read the specified ResourceQuota


```php
function getReadCoreV1NamespacedResourceQuota(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ResourceQuota |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = false;
$export = false;
$pretty = 'pretty';

$result = $coreV1->getReadCoreV1NamespacedResourceQuota($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_core_v1_namespaced_resource_quota"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateReplaceCoreV1NamespacedResourceQuota") updateReplaceCoreV1NamespacedResourceQuota

> replace the specified ResourceQuota


```php
function updateReplaceCoreV1NamespacedResourceQuota(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ResourceQuota |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1ResourceQuota();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->updateReplaceCoreV1NamespacedResourceQuota($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_namespaced_resource_quota"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1NamespacedResourceQuota") deleteCoreV1NamespacedResourceQuota

> delete a ResourceQuota


```php
function deleteCoreV1NamespacedResourceQuota(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ResourceQuota |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 51;
$orphanDependents = false;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1NamespacedResourceQuota($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_core_v1_namespaced_resource_quota"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.patchCoreV1NamespacedResourceQuota") patchCoreV1NamespacedResourceQuota

> partially update the specified ResourceQuota


```php
function patchCoreV1NamespacedResourceQuota(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ResourceQuota |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->patchCoreV1NamespacedResourceQuota($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_namespaced_resource_quota_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1NamespacedResourceQuotaStatus") getReadCoreV1NamespacedResourceQuotaStatus

> read status of the specified ResourceQuota


```php
function getReadCoreV1NamespacedResourceQuotaStatus(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ResourceQuota |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->getReadCoreV1NamespacedResourceQuotaStatus($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_core_v1_namespaced_resource_quota_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateReplaceCoreV1NamespacedResourceQuotaStatus") updateReplaceCoreV1NamespacedResourceQuotaStatus

> replace status of the specified ResourceQuota


```php
function updateReplaceCoreV1NamespacedResourceQuotaStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ResourceQuota |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1ResourceQuota();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->updateReplaceCoreV1NamespacedResourceQuotaStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_core_v1_namespaced_resource_quota_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.patchCoreV1NamespacedResourceQuotaStatus") patchCoreV1NamespacedResourceQuotaStatus

> partially update status of the specified ResourceQuota


```php
function patchCoreV1NamespacedResourceQuotaStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ResourceQuota |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->patchCoreV1NamespacedResourceQuotaStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_namespaced_secret"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1NamespacedSecret") listCoreV1NamespacedSecret

> list or watch objects of kind Secret


```php
function listCoreV1NamespacedSecret(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 51;
$watch = false;
$pretty = 'pretty';

$result = $coreV1->listCoreV1NamespacedSecret($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_core_v1_namespaced_secret"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createCoreV1NamespacedSecret") createCoreV1NamespacedSecret

> create a Secret


```php
function createCoreV1NamespacedSecret(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1Secret();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->createCoreV1NamespacedSecret($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_collection_namespaced_secret"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1CollectionNamespacedSecret") deleteCoreV1CollectionNamespacedSecret

> delete collection of Secret


```php
function deleteCoreV1CollectionNamespacedSecret(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 51;
$watch = false;
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1CollectionNamespacedSecret($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_namespaced_secret"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1NamespacedSecret") getReadCoreV1NamespacedSecret

> read the specified Secret


```php
function getReadCoreV1NamespacedSecret(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Secret |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = false;
$export = false;
$pretty = 'pretty';

$result = $coreV1->getReadCoreV1NamespacedSecret($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_core_v1_namespaced_secret"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateReplaceCoreV1NamespacedSecret") updateReplaceCoreV1NamespacedSecret

> replace the specified Secret


```php
function updateReplaceCoreV1NamespacedSecret(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Secret |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1Secret();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->updateReplaceCoreV1NamespacedSecret($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_namespaced_secret"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1NamespacedSecret") deleteCoreV1NamespacedSecret

> delete a Secret


```php
function deleteCoreV1NamespacedSecret(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Secret |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 143;
$orphanDependents = true;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1NamespacedSecret($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_core_v1_namespaced_secret"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.patchCoreV1NamespacedSecret") patchCoreV1NamespacedSecret

> partially update the specified Secret


```php
function patchCoreV1NamespacedSecret(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Secret |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->patchCoreV1NamespacedSecret($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_namespaced_service_account"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1NamespacedServiceAccount") listCoreV1NamespacedServiceAccount

> list or watch objects of kind ServiceAccount


```php
function listCoreV1NamespacedServiceAccount(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 143;
$watch = true;
$pretty = 'pretty';

$result = $coreV1->listCoreV1NamespacedServiceAccount($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_core_v1_namespaced_service_account"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createCoreV1NamespacedServiceAccount") createCoreV1NamespacedServiceAccount

> create a ServiceAccount


```php
function createCoreV1NamespacedServiceAccount(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1ServiceAccount();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->createCoreV1NamespacedServiceAccount($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_collection_namespaced_service_account"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1CollectionNamespacedServiceAccount") deleteCoreV1CollectionNamespacedServiceAccount

> delete collection of ServiceAccount


```php
function deleteCoreV1CollectionNamespacedServiceAccount(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 143;
$watch = true;
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1CollectionNamespacedServiceAccount($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_namespaced_service_account"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1NamespacedServiceAccount") getReadCoreV1NamespacedServiceAccount

> read the specified ServiceAccount


```php
function getReadCoreV1NamespacedServiceAccount(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ServiceAccount |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = true;
$export = true;
$pretty = 'pretty';

$result = $coreV1->getReadCoreV1NamespacedServiceAccount($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_core_v1_namespaced_service_account"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateReplaceCoreV1NamespacedServiceAccount") updateReplaceCoreV1NamespacedServiceAccount

> replace the specified ServiceAccount


```php
function updateReplaceCoreV1NamespacedServiceAccount(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ServiceAccount |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1ServiceAccount();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->updateReplaceCoreV1NamespacedServiceAccount($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_namespaced_service_account"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1NamespacedServiceAccount") deleteCoreV1NamespacedServiceAccount

> delete a ServiceAccount


```php
function deleteCoreV1NamespacedServiceAccount(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ServiceAccount |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 143;
$orphanDependents = true;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1NamespacedServiceAccount($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_core_v1_namespaced_service_account"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.patchCoreV1NamespacedServiceAccount") patchCoreV1NamespacedServiceAccount

> partially update the specified ServiceAccount


```php
function patchCoreV1NamespacedServiceAccount(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ServiceAccount |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->patchCoreV1NamespacedServiceAccount($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_namespaced_service"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1NamespacedService") listCoreV1NamespacedService

> list or watch objects of kind Service


```php
function listCoreV1NamespacedService(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 143;
$watch = true;
$pretty = 'pretty';

$result = $coreV1->listCoreV1NamespacedService($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_core_v1_namespaced_service"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createCoreV1NamespacedService") createCoreV1NamespacedService

> create a Service


```php
function createCoreV1NamespacedService(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1Service();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->createCoreV1NamespacedService($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_namespaced_service"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1NamespacedService") getReadCoreV1NamespacedService

> read the specified Service


```php
function getReadCoreV1NamespacedService(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = false;
$export = false;
$pretty = 'pretty';

$result = $coreV1->getReadCoreV1NamespacedService($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_core_v1_namespaced_service"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateReplaceCoreV1NamespacedService") updateReplaceCoreV1NamespacedService

> replace the specified Service


```php
function updateReplaceCoreV1NamespacedService(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1Service();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->updateReplaceCoreV1NamespacedService($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_namespaced_service"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1NamespacedService") deleteCoreV1NamespacedService

> delete a Service


```php
function deleteCoreV1NamespacedService(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1NamespacedService($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_core_v1_namespaced_service"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.patchCoreV1NamespacedService") patchCoreV1NamespacedService

> partially update the specified Service


```php
function patchCoreV1NamespacedService(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->patchCoreV1NamespacedService($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_connect_core_v1_get_namespaced_service_proxy"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getConnectCoreV1GetNamespacedServiceProxy") getConnectCoreV1GetNamespacedServiceProxy

> connect GET requests to proxy of Service


```php
function getConnectCoreV1GetNamespacedServiceProxy(
        $name,
        $mnamespace,
        $path = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Optional ```  | Path is the part of URLs that include service endpoints, suffixes, and parameters to use for the current proxy request to service. For example, the whole request URL is http://localhost/api/v1/namespaces/kube-system/services/elasticsearch-logging/_search?q=user:kimchy. Path is _search?q=user:kimchy. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->getConnectCoreV1GetNamespacedServiceProxy($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_connect_core_v1_put_namespaced_service_proxy"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateConnectCoreV1PutNamespacedServiceProxy") updateConnectCoreV1PutNamespacedServiceProxy

> connect PUT requests to proxy of Service


```php
function updateConnectCoreV1PutNamespacedServiceProxy(
        $name,
        $mnamespace,
        $path = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Optional ```  | Path is the part of URLs that include service endpoints, suffixes, and parameters to use for the current proxy request to service. For example, the whole request URL is http://localhost/api/v1/namespaces/kube-system/services/elasticsearch-logging/_search?q=user:kimchy. Path is _search?q=user:kimchy. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->updateConnectCoreV1PutNamespacedServiceProxy($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_connect_core_v1_post_namespaced_service_proxy"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createConnectCoreV1PostNamespacedServiceProxy") createConnectCoreV1PostNamespacedServiceProxy

> connect POST requests to proxy of Service


```php
function createConnectCoreV1PostNamespacedServiceProxy(
        $name,
        $mnamespace,
        $path = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Optional ```  | Path is the part of URLs that include service endpoints, suffixes, and parameters to use for the current proxy request to service. For example, the whole request URL is http://localhost/api/v1/namespaces/kube-system/services/elasticsearch-logging/_search?q=user:kimchy. Path is _search?q=user:kimchy. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->createConnectCoreV1PostNamespacedServiceProxy($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_connect_core_v1_delete_namespaced_service_proxy"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteConnectCoreV1DeleteNamespacedServiceProxy") deleteConnectCoreV1DeleteNamespacedServiceProxy

> connect DELETE requests to proxy of Service


```php
function deleteConnectCoreV1DeleteNamespacedServiceProxy(
        $name,
        $mnamespace,
        $path = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Optional ```  | Path is the part of URLs that include service endpoints, suffixes, and parameters to use for the current proxy request to service. For example, the whole request URL is http://localhost/api/v1/namespaces/kube-system/services/elasticsearch-logging/_search?q=user:kimchy. Path is _search?q=user:kimchy. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->deleteConnectCoreV1DeleteNamespacedServiceProxy($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_connect_core_v1_patch_namespaced_service_proxy"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateConnectCoreV1PatchNamespacedServiceProxy") updateConnectCoreV1PatchNamespacedServiceProxy

> connect PATCH requests to proxy of Service


```php
function updateConnectCoreV1PatchNamespacedServiceProxy(
        $name,
        $mnamespace,
        $path = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Optional ```  | Path is the part of URLs that include service endpoints, suffixes, and parameters to use for the current proxy request to service. For example, the whole request URL is http://localhost/api/v1/namespaces/kube-system/services/elasticsearch-logging/_search?q=user:kimchy. Path is _search?q=user:kimchy. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->updateConnectCoreV1PatchNamespacedServiceProxy($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_connect_core_v1_get_namespaced_service_proxy_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getConnectCoreV1GetNamespacedServiceProxyWithPath") getConnectCoreV1GetNamespacedServiceProxyWithPath

> connect GET requests to proxy of Service


```php
function getConnectCoreV1GetNamespacedServiceProxyWithPath(
        $name,
        $mnamespace,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->getConnectCoreV1GetNamespacedServiceProxyWithPath($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_connect_core_v1_put_namespaced_service_proxy_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateConnectCoreV1PutNamespacedServiceProxyWithPath") updateConnectCoreV1PutNamespacedServiceProxyWithPath

> connect PUT requests to proxy of Service


```php
function updateConnectCoreV1PutNamespacedServiceProxyWithPath(
        $name,
        $mnamespace,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->updateConnectCoreV1PutNamespacedServiceProxyWithPath($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_connect_core_v1_post_namespaced_service_proxy_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createConnectCoreV1PostNamespacedServiceProxyWithPath") createConnectCoreV1PostNamespacedServiceProxyWithPath

> connect POST requests to proxy of Service


```php
function createConnectCoreV1PostNamespacedServiceProxyWithPath(
        $name,
        $mnamespace,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->createConnectCoreV1PostNamespacedServiceProxyWithPath($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_connect_core_v1_delete_namespaced_service_proxy_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteConnectCoreV1DeleteNamespacedServiceProxyWithPath") deleteConnectCoreV1DeleteNamespacedServiceProxyWithPath

> connect DELETE requests to proxy of Service


```php
function deleteConnectCoreV1DeleteNamespacedServiceProxyWithPath(
        $name,
        $mnamespace,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->deleteConnectCoreV1DeleteNamespacedServiceProxyWithPath($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_connect_core_v1_patch_namespaced_service_proxy_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateConnectCoreV1PatchNamespacedServiceProxyWithPath") updateConnectCoreV1PatchNamespacedServiceProxyWithPath

> connect PATCH requests to proxy of Service


```php
function updateConnectCoreV1PatchNamespacedServiceProxyWithPath(
        $name,
        $mnamespace,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->updateConnectCoreV1PatchNamespacedServiceProxyWithPath($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_namespaced_service_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1NamespacedServiceStatus") getReadCoreV1NamespacedServiceStatus

> read status of the specified Service


```php
function getReadCoreV1NamespacedServiceStatus(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->getReadCoreV1NamespacedServiceStatus($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_core_v1_namespaced_service_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateReplaceCoreV1NamespacedServiceStatus") updateReplaceCoreV1NamespacedServiceStatus

> replace status of the specified Service


```php
function updateReplaceCoreV1NamespacedServiceStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1Service();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->updateReplaceCoreV1NamespacedServiceStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_core_v1_namespaced_service_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.patchCoreV1NamespacedServiceStatus") patchCoreV1NamespacedServiceStatus

> partially update status of the specified Service


```php
function patchCoreV1NamespacedServiceStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $coreV1->patchCoreV1NamespacedServiceStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_namespace"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1Namespace") getReadCoreV1Namespace

> read the specified Namespace


```php
function getReadCoreV1Namespace(
        $name,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Namespace |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$exact = false;
$export = false;
$pretty = 'pretty';

$result = $coreV1->getReadCoreV1Namespace($name, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_core_v1_namespace"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateReplaceCoreV1Namespace") updateReplaceCoreV1Namespace

> replace the specified Namespace


```php
function updateReplaceCoreV1Namespace(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Namespace |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1Namespace();
$name = 'name';
$pretty = 'pretty';

$result = $coreV1->updateReplaceCoreV1Namespace($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_namespace"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1Namespace") deleteCoreV1Namespace

> delete a Namespace


```php
function deleteCoreV1Namespace(
        $body,
        $name,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Namespace |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$gracePeriodSeconds = 192;
$orphanDependents = true;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1Namespace($body, $name, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_core_v1_namespace"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.patchCoreV1Namespace") patchCoreV1Namespace

> partially update the specified Namespace


```php
function patchCoreV1Namespace(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Namespace |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$pretty = 'pretty';

$result = $coreV1->patchCoreV1Namespace($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_core_v1_namespace_finalize"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateReplaceCoreV1NamespaceFinalize") updateReplaceCoreV1NamespaceFinalize

> replace finalize of the specified Namespace


```php
function updateReplaceCoreV1NamespaceFinalize(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Namespace |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1Namespace();
$name = 'name';
$pretty = 'pretty';

$result = $coreV1->updateReplaceCoreV1NamespaceFinalize($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_namespace_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1NamespaceStatus") getReadCoreV1NamespaceStatus

> read status of the specified Namespace


```php
function getReadCoreV1NamespaceStatus(
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Namespace |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$pretty = 'pretty';

$result = $coreV1->getReadCoreV1NamespaceStatus($name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_core_v1_namespace_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateReplaceCoreV1NamespaceStatus") updateReplaceCoreV1NamespaceStatus

> replace status of the specified Namespace


```php
function updateReplaceCoreV1NamespaceStatus(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Namespace |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1Namespace();
$name = 'name';
$pretty = 'pretty';

$result = $coreV1->updateReplaceCoreV1NamespaceStatus($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_core_v1_namespace_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.patchCoreV1NamespaceStatus") patchCoreV1NamespaceStatus

> partially update status of the specified Namespace


```php
function patchCoreV1NamespaceStatus(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Namespace |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$pretty = 'pretty';

$result = $coreV1->patchCoreV1NamespaceStatus($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_node"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1Node") listCoreV1Node

> list or watch objects of kind Node


```php
function listCoreV1Node(
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 192;
$watch = true;
$pretty = 'pretty';

$result = $coreV1->listCoreV1Node($fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_core_v1_node"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createCoreV1Node") createCoreV1Node

> create a Node


```php
function createCoreV1Node(
        $body,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1Node();
$pretty = 'pretty';

$result = $coreV1->createCoreV1Node($body, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_collection_node"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1CollectionNode") deleteCoreV1CollectionNode

> delete collection of Node


```php
function deleteCoreV1CollectionNode(
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 192;
$watch = true;
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1CollectionNode($fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_node"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1Node") getReadCoreV1Node

> read the specified Node


```php
function getReadCoreV1Node(
        $name,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Node |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$exact = true;
$export = true;
$pretty = 'pretty';

$result = $coreV1->getReadCoreV1Node($name, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_core_v1_node"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateReplaceCoreV1Node") updateReplaceCoreV1Node

> replace the specified Node


```php
function updateReplaceCoreV1Node(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Node |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1Node();
$name = 'name';
$pretty = 'pretty';

$result = $coreV1->updateReplaceCoreV1Node($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_node"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1Node") deleteCoreV1Node

> delete a Node


```php
function deleteCoreV1Node(
        $body,
        $name,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Node |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$gracePeriodSeconds = 192;
$orphanDependents = true;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1Node($body, $name, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_core_v1_node"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.patchCoreV1Node") patchCoreV1Node

> partially update the specified Node


```php
function patchCoreV1Node(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Node |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$pretty = 'pretty';

$result = $coreV1->patchCoreV1Node($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_connect_core_v1_get_node_proxy"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getConnectCoreV1GetNodeProxy") getConnectCoreV1GetNodeProxy

> connect GET requests to proxy of Node


```php
function getConnectCoreV1GetNodeProxy(
        $name,
        $path = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Node |
| path |  ``` Optional ```  | Path is the URL path to use for the current proxy request to node. |



#### Example Usage

```php
$name = 'name';
$path = 'path';

$result = $coreV1->getConnectCoreV1GetNodeProxy($name, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_connect_core_v1_put_node_proxy"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateConnectCoreV1PutNodeProxy") updateConnectCoreV1PutNodeProxy

> connect PUT requests to proxy of Node


```php
function updateConnectCoreV1PutNodeProxy(
        $name,
        $path = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Node |
| path |  ``` Optional ```  | Path is the URL path to use for the current proxy request to node. |



#### Example Usage

```php
$name = 'name';
$path = 'path';

$result = $coreV1->updateConnectCoreV1PutNodeProxy($name, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_connect_core_v1_post_node_proxy"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createConnectCoreV1PostNodeProxy") createConnectCoreV1PostNodeProxy

> connect POST requests to proxy of Node


```php
function createConnectCoreV1PostNodeProxy(
        $name,
        $path = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Node |
| path |  ``` Optional ```  | Path is the URL path to use for the current proxy request to node. |



#### Example Usage

```php
$name = 'name';
$path = 'path';

$result = $coreV1->createConnectCoreV1PostNodeProxy($name, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_connect_core_v1_delete_node_proxy"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteConnectCoreV1DeleteNodeProxy") deleteConnectCoreV1DeleteNodeProxy

> connect DELETE requests to proxy of Node


```php
function deleteConnectCoreV1DeleteNodeProxy(
        $name,
        $path = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Node |
| path |  ``` Optional ```  | Path is the URL path to use for the current proxy request to node. |



#### Example Usage

```php
$name = 'name';
$path = 'path';

$result = $coreV1->deleteConnectCoreV1DeleteNodeProxy($name, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_connect_core_v1_patch_node_proxy"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateConnectCoreV1PatchNodeProxy") updateConnectCoreV1PatchNodeProxy

> connect PATCH requests to proxy of Node


```php
function updateConnectCoreV1PatchNodeProxy(
        $name,
        $path = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Node |
| path |  ``` Optional ```  | Path is the URL path to use for the current proxy request to node. |



#### Example Usage

```php
$name = 'name';
$path = 'path';

$result = $coreV1->updateConnectCoreV1PatchNodeProxy($name, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_connect_core_v1_get_node_proxy_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getConnectCoreV1GetNodeProxyWithPath") getConnectCoreV1GetNodeProxyWithPath

> connect GET requests to proxy of Node


```php
function getConnectCoreV1GetNodeProxyWithPath(
        $name,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Node |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$path = 'path';

$result = $coreV1->getConnectCoreV1GetNodeProxyWithPath($name, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_connect_core_v1_put_node_proxy_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateConnectCoreV1PutNodeProxyWithPath") updateConnectCoreV1PutNodeProxyWithPath

> connect PUT requests to proxy of Node


```php
function updateConnectCoreV1PutNodeProxyWithPath(
        $name,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Node |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$path = 'path';

$result = $coreV1->updateConnectCoreV1PutNodeProxyWithPath($name, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_connect_core_v1_post_node_proxy_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createConnectCoreV1PostNodeProxyWithPath") createConnectCoreV1PostNodeProxyWithPath

> connect POST requests to proxy of Node


```php
function createConnectCoreV1PostNodeProxyWithPath(
        $name,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Node |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$path = 'path';

$result = $coreV1->createConnectCoreV1PostNodeProxyWithPath($name, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_connect_core_v1_delete_node_proxy_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteConnectCoreV1DeleteNodeProxyWithPath") deleteConnectCoreV1DeleteNodeProxyWithPath

> connect DELETE requests to proxy of Node


```php
function deleteConnectCoreV1DeleteNodeProxyWithPath(
        $name,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Node |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$path = 'path';

$result = $coreV1->deleteConnectCoreV1DeleteNodeProxyWithPath($name, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_connect_core_v1_patch_node_proxy_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateConnectCoreV1PatchNodeProxyWithPath") updateConnectCoreV1PatchNodeProxyWithPath

> connect PATCH requests to proxy of Node


```php
function updateConnectCoreV1PatchNodeProxyWithPath(
        $name,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Node |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$path = 'path';

$result = $coreV1->updateConnectCoreV1PatchNodeProxyWithPath($name, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_node_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1NodeStatus") getReadCoreV1NodeStatus

> read status of the specified Node


```php
function getReadCoreV1NodeStatus(
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Node |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$pretty = 'pretty';

$result = $coreV1->getReadCoreV1NodeStatus($name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_core_v1_node_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateReplaceCoreV1NodeStatus") updateReplaceCoreV1NodeStatus

> replace status of the specified Node


```php
function updateReplaceCoreV1NodeStatus(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Node |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1Node();
$name = 'name';
$pretty = 'pretty';

$result = $coreV1->updateReplaceCoreV1NodeStatus($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_core_v1_node_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.patchCoreV1NodeStatus") patchCoreV1NodeStatus

> partially update status of the specified Node


```php
function patchCoreV1NodeStatus(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Node |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$pretty = 'pretty';

$result = $coreV1->patchCoreV1NodeStatus($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_persistent_volume_claim_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1PersistentVolumeClaimForAllNamespaces") listCoreV1PersistentVolumeClaimForAllNamespaces

> list or watch objects of kind PersistentVolumeClaim


```php
function listCoreV1PersistentVolumeClaimForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 29;
$watch = false;

$result = $coreV1->listCoreV1PersistentVolumeClaimForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_persistent_volume"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1PersistentVolume") listCoreV1PersistentVolume

> list or watch objects of kind PersistentVolume


```php
function listCoreV1PersistentVolume(
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 29;
$watch = false;
$pretty = 'pretty';

$result = $coreV1->listCoreV1PersistentVolume($fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_core_v1_persistent_volume"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createCoreV1PersistentVolume") createCoreV1PersistentVolume

> create a PersistentVolume


```php
function createCoreV1PersistentVolume(
        $body,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1PersistentVolume();
$pretty = 'pretty';

$result = $coreV1->createCoreV1PersistentVolume($body, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_collection_persistent_volume"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1CollectionPersistentVolume") deleteCoreV1CollectionPersistentVolume

> delete collection of PersistentVolume


```php
function deleteCoreV1CollectionPersistentVolume(
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 29;
$watch = false;
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1CollectionPersistentVolume($fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_persistent_volume"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1PersistentVolume") getReadCoreV1PersistentVolume

> read the specified PersistentVolume


```php
function getReadCoreV1PersistentVolume(
        $name,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the PersistentVolume |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$exact = false;
$export = false;
$pretty = 'pretty';

$result = $coreV1->getReadCoreV1PersistentVolume($name, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_core_v1_persistent_volume"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateReplaceCoreV1PersistentVolume") updateReplaceCoreV1PersistentVolume

> replace the specified PersistentVolume


```php
function updateReplaceCoreV1PersistentVolume(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the PersistentVolume |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1PersistentVolume();
$name = 'name';
$pretty = 'pretty';

$result = $coreV1->updateReplaceCoreV1PersistentVolume($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_core_v1_persistent_volume"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteCoreV1PersistentVolume") deleteCoreV1PersistentVolume

> delete a PersistentVolume


```php
function deleteCoreV1PersistentVolume(
        $body,
        $name,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the PersistentVolume |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$gracePeriodSeconds = 29;
$orphanDependents = false;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $coreV1->deleteCoreV1PersistentVolume($body, $name, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_core_v1_persistent_volume"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.patchCoreV1PersistentVolume") patchCoreV1PersistentVolume

> partially update the specified PersistentVolume


```php
function patchCoreV1PersistentVolume(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the PersistentVolume |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$pretty = 'pretty';

$result = $coreV1->patchCoreV1PersistentVolume($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_core_v1_persistent_volume_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getReadCoreV1PersistentVolumeStatus") getReadCoreV1PersistentVolumeStatus

> read status of the specified PersistentVolume


```php
function getReadCoreV1PersistentVolumeStatus(
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the PersistentVolume |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$pretty = 'pretty';

$result = $coreV1->getReadCoreV1PersistentVolumeStatus($name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_core_v1_persistent_volume_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateReplaceCoreV1PersistentVolumeStatus") updateReplaceCoreV1PersistentVolumeStatus

> replace status of the specified PersistentVolume


```php
function updateReplaceCoreV1PersistentVolumeStatus(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the PersistentVolume |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApiV1PersistentVolume();
$name = 'name';
$pretty = 'pretty';

$result = $coreV1->updateReplaceCoreV1PersistentVolumeStatus($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_core_v1_persistent_volume_status"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.patchCoreV1PersistentVolumeStatus") patchCoreV1PersistentVolumeStatus

> partially update status of the specified PersistentVolume


```php
function patchCoreV1PersistentVolumeStatus(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the PersistentVolume |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$pretty = 'pretty';

$result = $coreV1->patchCoreV1PersistentVolumeStatus($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_pod_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1PodForAllNamespaces") listCoreV1PodForAllNamespaces

> list or watch objects of kind Pod


```php
function listCoreV1PodForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 29;
$watch = false;

$result = $coreV1->listCoreV1PodForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_pod_template_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1PodTemplateForAllNamespaces") listCoreV1PodTemplateForAllNamespaces

> list or watch objects of kind PodTemplate


```php
function listCoreV1PodTemplateForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 242;
$watch = true;

$result = $coreV1->listCoreV1PodTemplateForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_proxy_core_v1_get_namespaced_pod"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getProxyCoreV1GETNamespacedPod") getProxyCoreV1GETNamespacedPod

> proxy GET requests to Pod


```php
function getProxyCoreV1GETNamespacedPod(
        $name,
        $mnamespace)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';

$result = $coreV1->getProxyCoreV1GETNamespacedPod($name, $mnamespace);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_proxy_core_v1_put_namespaced_pod"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateProxyCoreV1PUTNamespacedPod") updateProxyCoreV1PUTNamespacedPod

> proxy PUT requests to Pod


```php
function updateProxyCoreV1PUTNamespacedPod(
        $name,
        $mnamespace)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';

$result = $coreV1->updateProxyCoreV1PUTNamespacedPod($name, $mnamespace);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_proxy_core_v1_post_namespaced_pod"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createProxyCoreV1POSTNamespacedPod") createProxyCoreV1POSTNamespacedPod

> proxy POST requests to Pod


```php
function createProxyCoreV1POSTNamespacedPod(
        $name,
        $mnamespace)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';

$result = $coreV1->createProxyCoreV1POSTNamespacedPod($name, $mnamespace);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_proxy_core_v1_delete_namespaced_pod"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteProxyCoreV1DELETENamespacedPod") deleteProxyCoreV1DELETENamespacedPod

> proxy DELETE requests to Pod


```php
function deleteProxyCoreV1DELETENamespacedPod(
        $name,
        $mnamespace)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';

$result = $coreV1->deleteProxyCoreV1DELETENamespacedPod($name, $mnamespace);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_proxy_core_v1_patch_namespaced_pod"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateProxyCoreV1PATCHNamespacedPod") updateProxyCoreV1PATCHNamespacedPod

> proxy PATCH requests to Pod


```php
function updateProxyCoreV1PATCHNamespacedPod(
        $name,
        $mnamespace)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';

$result = $coreV1->updateProxyCoreV1PATCHNamespacedPod($name, $mnamespace);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_proxy_core_v1_get_namespaced_pod_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getProxyCoreV1GETNamespacedPodWithPath") getProxyCoreV1GETNamespacedPodWithPath

> proxy GET requests to Pod


```php
function getProxyCoreV1GETNamespacedPodWithPath(
        $name,
        $mnamespace,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->getProxyCoreV1GETNamespacedPodWithPath($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_proxy_core_v1_put_namespaced_pod_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateProxyCoreV1PUTNamespacedPodWithPath") updateProxyCoreV1PUTNamespacedPodWithPath

> proxy PUT requests to Pod


```php
function updateProxyCoreV1PUTNamespacedPodWithPath(
        $name,
        $mnamespace,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->updateProxyCoreV1PUTNamespacedPodWithPath($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_proxy_core_v1_post_namespaced_pod_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createProxyCoreV1POSTNamespacedPodWithPath") createProxyCoreV1POSTNamespacedPodWithPath

> proxy POST requests to Pod


```php
function createProxyCoreV1POSTNamespacedPodWithPath(
        $name,
        $mnamespace,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->createProxyCoreV1POSTNamespacedPodWithPath($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_proxy_core_v1_delete_namespaced_pod_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteProxyCoreV1DELETENamespacedPodWithPath") deleteProxyCoreV1DELETENamespacedPodWithPath

> proxy DELETE requests to Pod


```php
function deleteProxyCoreV1DELETENamespacedPodWithPath(
        $name,
        $mnamespace,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->deleteProxyCoreV1DELETENamespacedPodWithPath($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_proxy_core_v1_patch_namespaced_pod_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateProxyCoreV1PATCHNamespacedPodWithPath") updateProxyCoreV1PATCHNamespacedPodWithPath

> proxy PATCH requests to Pod


```php
function updateProxyCoreV1PATCHNamespacedPodWithPath(
        $name,
        $mnamespace,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->updateProxyCoreV1PATCHNamespacedPodWithPath($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_proxy_core_v1_get_namespaced_service"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getProxyCoreV1GETNamespacedService") getProxyCoreV1GETNamespacedService

> proxy GET requests to Service


```php
function getProxyCoreV1GETNamespacedService(
        $name,
        $mnamespace)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';

$result = $coreV1->getProxyCoreV1GETNamespacedService($name, $mnamespace);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_proxy_core_v1_put_namespaced_service"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateProxyCoreV1PUTNamespacedService") updateProxyCoreV1PUTNamespacedService

> proxy PUT requests to Service


```php
function updateProxyCoreV1PUTNamespacedService(
        $name,
        $mnamespace)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';

$result = $coreV1->updateProxyCoreV1PUTNamespacedService($name, $mnamespace);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_proxy_core_v1_post_namespaced_service"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createProxyCoreV1POSTNamespacedService") createProxyCoreV1POSTNamespacedService

> proxy POST requests to Service


```php
function createProxyCoreV1POSTNamespacedService(
        $name,
        $mnamespace)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';

$result = $coreV1->createProxyCoreV1POSTNamespacedService($name, $mnamespace);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_proxy_core_v1_delete_namespaced_service"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteProxyCoreV1DELETENamespacedService") deleteProxyCoreV1DELETENamespacedService

> proxy DELETE requests to Service


```php
function deleteProxyCoreV1DELETENamespacedService(
        $name,
        $mnamespace)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';

$result = $coreV1->deleteProxyCoreV1DELETENamespacedService($name, $mnamespace);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_proxy_core_v1_patch_namespaced_service"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateProxyCoreV1PATCHNamespacedService") updateProxyCoreV1PATCHNamespacedService

> proxy PATCH requests to Service


```php
function updateProxyCoreV1PATCHNamespacedService(
        $name,
        $mnamespace)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';

$result = $coreV1->updateProxyCoreV1PATCHNamespacedService($name, $mnamespace);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_proxy_core_v1_get_namespaced_service_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getProxyCoreV1GETNamespacedServiceWithPath") getProxyCoreV1GETNamespacedServiceWithPath

> proxy GET requests to Service


```php
function getProxyCoreV1GETNamespacedServiceWithPath(
        $name,
        $mnamespace,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->getProxyCoreV1GETNamespacedServiceWithPath($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_proxy_core_v1_put_namespaced_service_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateProxyCoreV1PUTNamespacedServiceWithPath") updateProxyCoreV1PUTNamespacedServiceWithPath

> proxy PUT requests to Service


```php
function updateProxyCoreV1PUTNamespacedServiceWithPath(
        $name,
        $mnamespace,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->updateProxyCoreV1PUTNamespacedServiceWithPath($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_proxy_core_v1_post_namespaced_service_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createProxyCoreV1POSTNamespacedServiceWithPath") createProxyCoreV1POSTNamespacedServiceWithPath

> proxy POST requests to Service


```php
function createProxyCoreV1POSTNamespacedServiceWithPath(
        $name,
        $mnamespace,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->createProxyCoreV1POSTNamespacedServiceWithPath($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_proxy_core_v1_delete_namespaced_service_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteProxyCoreV1DELETENamespacedServiceWithPath") deleteProxyCoreV1DELETENamespacedServiceWithPath

> proxy DELETE requests to Service


```php
function deleteProxyCoreV1DELETENamespacedServiceWithPath(
        $name,
        $mnamespace,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->deleteProxyCoreV1DELETENamespacedServiceWithPath($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_proxy_core_v1_patch_namespaced_service_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateProxyCoreV1PATCHNamespacedServiceWithPath") updateProxyCoreV1PATCHNamespacedServiceWithPath

> proxy PATCH requests to Service


```php
function updateProxyCoreV1PATCHNamespacedServiceWithPath(
        $name,
        $mnamespace,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$path = 'path';

$result = $coreV1->updateProxyCoreV1PATCHNamespacedServiceWithPath($name, $mnamespace, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_proxy_core_v1_get_node"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getProxyCoreV1GETNode") getProxyCoreV1GETNode

> proxy GET requests to Node


```php
function getProxyCoreV1GETNode($name)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Node |



#### Example Usage

```php
$name = 'name';

$result = $coreV1->getProxyCoreV1GETNode($name);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_proxy_core_v1_put_node"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateProxyCoreV1PUTNode") updateProxyCoreV1PUTNode

> proxy PUT requests to Node


```php
function updateProxyCoreV1PUTNode($name)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Node |



#### Example Usage

```php
$name = 'name';

$result = $coreV1->updateProxyCoreV1PUTNode($name);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_proxy_core_v1_post_node"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createProxyCoreV1POSTNode") createProxyCoreV1POSTNode

> proxy POST requests to Node


```php
function createProxyCoreV1POSTNode($name)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Node |



#### Example Usage

```php
$name = 'name';

$result = $coreV1->createProxyCoreV1POSTNode($name);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_proxy_core_v1_delete_node"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteProxyCoreV1DELETENode") deleteProxyCoreV1DELETENode

> proxy DELETE requests to Node


```php
function deleteProxyCoreV1DELETENode($name)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Node |



#### Example Usage

```php
$name = 'name';

$result = $coreV1->deleteProxyCoreV1DELETENode($name);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_proxy_core_v1_patch_node"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateProxyCoreV1PATCHNode") updateProxyCoreV1PATCHNode

> proxy PATCH requests to Node


```php
function updateProxyCoreV1PATCHNode($name)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Node |



#### Example Usage

```php
$name = 'name';

$result = $coreV1->updateProxyCoreV1PATCHNode($name);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_proxy_core_v1_get_node_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getProxyCoreV1GETNodeWithPath") getProxyCoreV1GETNodeWithPath

> proxy GET requests to Node


```php
function getProxyCoreV1GETNodeWithPath(
        $name,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Node |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$path = 'path';

$result = $coreV1->getProxyCoreV1GETNodeWithPath($name, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_proxy_core_v1_put_node_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateProxyCoreV1PUTNodeWithPath") updateProxyCoreV1PUTNodeWithPath

> proxy PUT requests to Node


```php
function updateProxyCoreV1PUTNodeWithPath(
        $name,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Node |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$path = 'path';

$result = $coreV1->updateProxyCoreV1PUTNodeWithPath($name, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_proxy_core_v1_post_node_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.createProxyCoreV1POSTNodeWithPath") createProxyCoreV1POSTNodeWithPath

> proxy POST requests to Node


```php
function createProxyCoreV1POSTNodeWithPath(
        $name,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Node |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$path = 'path';

$result = $coreV1->createProxyCoreV1POSTNodeWithPath($name, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_proxy_core_v1_delete_node_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.deleteProxyCoreV1DELETENodeWithPath") deleteProxyCoreV1DELETENodeWithPath

> proxy DELETE requests to Node


```php
function deleteProxyCoreV1DELETENodeWithPath(
        $name,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Node |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$path = 'path';

$result = $coreV1->deleteProxyCoreV1DELETENodeWithPath($name, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_proxy_core_v1_patch_node_with_path"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.updateProxyCoreV1PATCHNodeWithPath") updateProxyCoreV1PATCHNodeWithPath

> proxy PATCH requests to Node


```php
function updateProxyCoreV1PATCHNodeWithPath(
        $name,
        $path)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Node |
| path |  ``` Required ```  | path to the resource |



#### Example Usage

```php
$name = 'name';
$path = 'path';

$result = $coreV1->updateProxyCoreV1PATCHNodeWithPath($name, $path);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_replication_controller_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1ReplicationControllerForAllNamespaces") listCoreV1ReplicationControllerForAllNamespaces

> list or watch objects of kind ReplicationController


```php
function listCoreV1ReplicationControllerForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 79;
$watch = false;

$result = $coreV1->listCoreV1ReplicationControllerForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_resource_quota_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1ResourceQuotaForAllNamespaces") listCoreV1ResourceQuotaForAllNamespaces

> list or watch objects of kind ResourceQuota


```php
function listCoreV1ResourceQuotaForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 79;
$watch = false;

$result = $coreV1->listCoreV1ResourceQuotaForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_secret_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1SecretForAllNamespaces") listCoreV1SecretForAllNamespaces

> list or watch objects of kind Secret


```php
function listCoreV1SecretForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 79;
$watch = false;

$result = $coreV1->listCoreV1SecretForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_service_account_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1ServiceAccountForAllNamespaces") listCoreV1ServiceAccountForAllNamespaces

> list or watch objects of kind ServiceAccount


```php
function listCoreV1ServiceAccountForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 79;
$watch = false;

$result = $coreV1->listCoreV1ServiceAccountForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_core_v1_service_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.listCoreV1ServiceForAllNamespaces") listCoreV1ServiceForAllNamespaces

> list or watch objects of kind Service


```php
function listCoreV1ServiceForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 79;
$watch = false;

$result = $coreV1->listCoreV1ServiceForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_config_map_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1ConfigMapListForAllNamespaces") getWatchCoreV1ConfigMapListForAllNamespaces

> watch individual changes to a list of ConfigMap


```php
function getWatchCoreV1ConfigMapListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 79;
$watch = false;

$result = $coreV1->getWatchCoreV1ConfigMapListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_endpoints_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1EndpointsListForAllNamespaces") getWatchCoreV1EndpointsListForAllNamespaces

> watch individual changes to a list of Endpoints


```php
function getWatchCoreV1EndpointsListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 79;
$watch = false;

$result = $coreV1->getWatchCoreV1EndpointsListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_event_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1EventListForAllNamespaces") getWatchCoreV1EventListForAllNamespaces

> watch individual changes to a list of Event


```php
function getWatchCoreV1EventListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 79;
$watch = false;

$result = $coreV1->getWatchCoreV1EventListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_limit_range_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1LimitRangeListForAllNamespaces") getWatchCoreV1LimitRangeListForAllNamespaces

> watch individual changes to a list of LimitRange


```php
function getWatchCoreV1LimitRangeListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 79;
$watch = false;

$result = $coreV1->getWatchCoreV1LimitRangeListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespace_list"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NamespaceList") getWatchCoreV1NamespaceList

> watch individual changes to a list of Namespace


```php
function getWatchCoreV1NamespaceList(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 79;
$watch = false;

$result = $coreV1->getWatchCoreV1NamespaceList($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespaced_config_map_list"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NamespacedConfigMapList") getWatchCoreV1NamespacedConfigMapList

> watch individual changes to a list of ConfigMap


```php
function getWatchCoreV1NamespacedConfigMapList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 79;
$watch = false;

$result = $coreV1->getWatchCoreV1NamespacedConfigMapList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespaced_config_map"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NamespacedConfigMap") getWatchCoreV1NamespacedConfigMap

> watch changes to an object of kind ConfigMap


```php
function getWatchCoreV1NamespacedConfigMap(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ConfigMap |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 170;
$watch = true;

$result = $coreV1->getWatchCoreV1NamespacedConfigMap($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespaced_endpoints_list"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NamespacedEndpointsList") getWatchCoreV1NamespacedEndpointsList

> watch individual changes to a list of Endpoints


```php
function getWatchCoreV1NamespacedEndpointsList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 170;
$watch = true;

$result = $coreV1->getWatchCoreV1NamespacedEndpointsList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespaced_endpoints"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NamespacedEndpoints") getWatchCoreV1NamespacedEndpoints

> watch changes to an object of kind Endpoints


```php
function getWatchCoreV1NamespacedEndpoints(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Endpoints |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 170;
$watch = true;

$result = $coreV1->getWatchCoreV1NamespacedEndpoints($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespaced_event_list"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NamespacedEventList") getWatchCoreV1NamespacedEventList

> watch individual changes to a list of Event


```php
function getWatchCoreV1NamespacedEventList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 170;
$watch = true;

$result = $coreV1->getWatchCoreV1NamespacedEventList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespaced_event"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NamespacedEvent") getWatchCoreV1NamespacedEvent

> watch changes to an object of kind Event


```php
function getWatchCoreV1NamespacedEvent(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Event |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 170;
$watch = true;

$result = $coreV1->getWatchCoreV1NamespacedEvent($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespaced_limit_range_list"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NamespacedLimitRangeList") getWatchCoreV1NamespacedLimitRangeList

> watch individual changes to a list of LimitRange


```php
function getWatchCoreV1NamespacedLimitRangeList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 170;
$watch = true;

$result = $coreV1->getWatchCoreV1NamespacedLimitRangeList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespaced_limit_range"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NamespacedLimitRange") getWatchCoreV1NamespacedLimitRange

> watch changes to an object of kind LimitRange


```php
function getWatchCoreV1NamespacedLimitRange(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the LimitRange |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 170;
$watch = true;

$result = $coreV1->getWatchCoreV1NamespacedLimitRange($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespaced_persistent_volume_claim_list"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NamespacedPersistentVolumeClaimList") getWatchCoreV1NamespacedPersistentVolumeClaimList

> watch individual changes to a list of PersistentVolumeClaim


```php
function getWatchCoreV1NamespacedPersistentVolumeClaimList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 170;
$watch = true;

$result = $coreV1->getWatchCoreV1NamespacedPersistentVolumeClaimList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespaced_persistent_volume_claim"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NamespacedPersistentVolumeClaim") getWatchCoreV1NamespacedPersistentVolumeClaim

> watch changes to an object of kind PersistentVolumeClaim


```php
function getWatchCoreV1NamespacedPersistentVolumeClaim(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the PersistentVolumeClaim |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 170;
$watch = true;

$result = $coreV1->getWatchCoreV1NamespacedPersistentVolumeClaim($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespaced_pod_list"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NamespacedPodList") getWatchCoreV1NamespacedPodList

> watch individual changes to a list of Pod


```php
function getWatchCoreV1NamespacedPodList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 170;
$watch = true;

$result = $coreV1->getWatchCoreV1NamespacedPodList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespaced_pod"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NamespacedPod") getWatchCoreV1NamespacedPod

> watch changes to an object of kind Pod


```php
function getWatchCoreV1NamespacedPod(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Pod |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 128;
$watch = true;

$result = $coreV1->getWatchCoreV1NamespacedPod($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespaced_pod_template_list"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NamespacedPodTemplateList") getWatchCoreV1NamespacedPodTemplateList

> watch individual changes to a list of PodTemplate


```php
function getWatchCoreV1NamespacedPodTemplateList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 128;
$watch = true;

$result = $coreV1->getWatchCoreV1NamespacedPodTemplateList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespaced_pod_template"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NamespacedPodTemplate") getWatchCoreV1NamespacedPodTemplate

> watch changes to an object of kind PodTemplate


```php
function getWatchCoreV1NamespacedPodTemplate(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the PodTemplate |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 128;
$watch = true;

$result = $coreV1->getWatchCoreV1NamespacedPodTemplate($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespaced_replication_controller_list"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NamespacedReplicationControllerList") getWatchCoreV1NamespacedReplicationControllerList

> watch individual changes to a list of ReplicationController


```php
function getWatchCoreV1NamespacedReplicationControllerList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 128;
$watch = true;

$result = $coreV1->getWatchCoreV1NamespacedReplicationControllerList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespaced_replication_controller"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NamespacedReplicationController") getWatchCoreV1NamespacedReplicationController

> watch changes to an object of kind ReplicationController


```php
function getWatchCoreV1NamespacedReplicationController(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ReplicationController |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 128;
$watch = true;

$result = $coreV1->getWatchCoreV1NamespacedReplicationController($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespaced_resource_quota_list"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NamespacedResourceQuotaList") getWatchCoreV1NamespacedResourceQuotaList

> watch individual changes to a list of ResourceQuota


```php
function getWatchCoreV1NamespacedResourceQuotaList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 128;
$watch = true;

$result = $coreV1->getWatchCoreV1NamespacedResourceQuotaList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespaced_resource_quota"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NamespacedResourceQuota") getWatchCoreV1NamespacedResourceQuota

> watch changes to an object of kind ResourceQuota


```php
function getWatchCoreV1NamespacedResourceQuota(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ResourceQuota |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 128;
$watch = true;

$result = $coreV1->getWatchCoreV1NamespacedResourceQuota($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespaced_secret_list"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NamespacedSecretList") getWatchCoreV1NamespacedSecretList

> watch individual changes to a list of Secret


```php
function getWatchCoreV1NamespacedSecretList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 128;
$watch = true;

$result = $coreV1->getWatchCoreV1NamespacedSecretList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespaced_secret"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NamespacedSecret") getWatchCoreV1NamespacedSecret

> watch changes to an object of kind Secret


```php
function getWatchCoreV1NamespacedSecret(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Secret |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 128;
$watch = true;

$result = $coreV1->getWatchCoreV1NamespacedSecret($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespaced_service_account_list"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NamespacedServiceAccountList") getWatchCoreV1NamespacedServiceAccountList

> watch individual changes to a list of ServiceAccount


```php
function getWatchCoreV1NamespacedServiceAccountList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 128;
$watch = true;

$result = $coreV1->getWatchCoreV1NamespacedServiceAccountList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespaced_service_account"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NamespacedServiceAccount") getWatchCoreV1NamespacedServiceAccount

> watch changes to an object of kind ServiceAccount


```php
function getWatchCoreV1NamespacedServiceAccount(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ServiceAccount |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 220;
$watch = true;

$result = $coreV1->getWatchCoreV1NamespacedServiceAccount($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespaced_service_list"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NamespacedServiceList") getWatchCoreV1NamespacedServiceList

> watch individual changes to a list of Service


```php
function getWatchCoreV1NamespacedServiceList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 220;
$watch = true;

$result = $coreV1->getWatchCoreV1NamespacedServiceList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespaced_service"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NamespacedService") getWatchCoreV1NamespacedService

> watch changes to an object of kind Service


```php
function getWatchCoreV1NamespacedService(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Service |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 220;
$watch = true;

$result = $coreV1->getWatchCoreV1NamespacedService($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_namespace"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1Namespace") getWatchCoreV1Namespace

> watch changes to an object of kind Namespace


```php
function getWatchCoreV1Namespace(
        $name,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Namespace |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 220;
$watch = true;

$result = $coreV1->getWatchCoreV1Namespace($name, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_node_list"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1NodeList") getWatchCoreV1NodeList

> watch individual changes to a list of Node


```php
function getWatchCoreV1NodeList(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 220;
$watch = true;

$result = $coreV1->getWatchCoreV1NodeList($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_node"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1Node") getWatchCoreV1Node

> watch changes to an object of kind Node


```php
function getWatchCoreV1Node(
        $name,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Node |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 220;
$watch = true;

$result = $coreV1->getWatchCoreV1Node($name, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_persistent_volume_claim_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1PersistentVolumeClaimListForAllNamespaces") getWatchCoreV1PersistentVolumeClaimListForAllNamespaces

> watch individual changes to a list of PersistentVolumeClaim


```php
function getWatchCoreV1PersistentVolumeClaimListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 220;
$watch = true;

$result = $coreV1->getWatchCoreV1PersistentVolumeClaimListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_persistent_volume_list"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1PersistentVolumeList") getWatchCoreV1PersistentVolumeList

> watch individual changes to a list of PersistentVolume


```php
function getWatchCoreV1PersistentVolumeList(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 220;
$watch = true;

$result = $coreV1->getWatchCoreV1PersistentVolumeList($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_persistent_volume"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1PersistentVolume") getWatchCoreV1PersistentVolume

> watch changes to an object of kind PersistentVolume


```php
function getWatchCoreV1PersistentVolume(
        $name,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the PersistentVolume |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 220;
$watch = true;

$result = $coreV1->getWatchCoreV1PersistentVolume($name, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_pod_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1PodListForAllNamespaces") getWatchCoreV1PodListForAllNamespaces

> watch individual changes to a list of Pod


```php
function getWatchCoreV1PodListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 220;
$watch = true;

$result = $coreV1->getWatchCoreV1PodListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_pod_template_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1PodTemplateListForAllNamespaces") getWatchCoreV1PodTemplateListForAllNamespaces

> watch individual changes to a list of PodTemplate


```php
function getWatchCoreV1PodTemplateListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 220;
$watch = true;

$result = $coreV1->getWatchCoreV1PodTemplateListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_replication_controller_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1ReplicationControllerListForAllNamespaces") getWatchCoreV1ReplicationControllerListForAllNamespaces

> watch individual changes to a list of ReplicationController


```php
function getWatchCoreV1ReplicationControllerListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 178;
$watch = true;

$result = $coreV1->getWatchCoreV1ReplicationControllerListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_resource_quota_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1ResourceQuotaListForAllNamespaces") getWatchCoreV1ResourceQuotaListForAllNamespaces

> watch individual changes to a list of ResourceQuota


```php
function getWatchCoreV1ResourceQuotaListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 178;
$watch = true;

$result = $coreV1->getWatchCoreV1ResourceQuotaListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_secret_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1SecretListForAllNamespaces") getWatchCoreV1SecretListForAllNamespaces

> watch individual changes to a list of Secret


```php
function getWatchCoreV1SecretListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 178;
$watch = true;

$result = $coreV1->getWatchCoreV1SecretListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_service_account_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1ServiceAccountListForAllNamespaces") getWatchCoreV1ServiceAccountListForAllNamespaces

> watch individual changes to a list of ServiceAccount


```php
function getWatchCoreV1ServiceAccountListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 178;
$watch = true;

$result = $coreV1->getWatchCoreV1ServiceAccountListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_core_v1_service_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".CoreV1Controller.getWatchCoreV1ServiceListForAllNamespaces") getWatchCoreV1ServiceListForAllNamespaces

> watch individual changes to a list of Service


```php
function getWatchCoreV1ServiceListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 178;
$watch = true;

$result = $coreV1->getWatchCoreV1ServiceListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="apis_controller"></a>![Class: ](https://apidocs.io/img/class.png ".ApisController") ApisController

### Get singleton instance

The singleton instance of the ``` ApisController ``` class can be accessed from the API Client.

```php
$apis = $client->getApis();
```

### <a name="get_api_versions"></a>![Method: ](https://apidocs.io/img/method.png ".ApisController.getAPIVersions") getAPIVersions

> get available API versions


```php
function getAPIVersions()
```

#### Example Usage

```php

$result = $apis->getAPIVersions();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="apps_controller"></a>![Class: ](https://apidocs.io/img/class.png ".AppsController") AppsController

### Get singleton instance

The singleton instance of the ``` AppsController ``` class can be accessed from the API Client.

```php
$apps = $client->getApps();
```

### <a name="get_apps_api_group"></a>![Method: ](https://apidocs.io/img/method.png ".AppsController.getAppsAPIGroup") getAppsAPIGroup

> get information of a group


```php
function getAppsAPIGroup()
```

#### Example Usage

```php

$result = $apps->getAppsAPIGroup();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="apps_v1beta1_controller"></a>![Class: ](https://apidocs.io/img/class.png ".AppsV1beta1Controller") AppsV1beta1Controller

### Get singleton instance

The singleton instance of the ``` AppsV1beta1Controller ``` class can be accessed from the API Client.

```php
$appsV1beta1 = $client->getAppsV1beta1();
```

### <a name="get_apps_v1beta1_api_resources"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.getAppsV1beta1APIResources") getAppsV1beta1APIResources

> get available resources


```php
function getAppsV1beta1APIResources()
```

#### Example Usage

```php

$result = $appsV1beta1->getAppsV1beta1APIResources();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_apps_v1beta1_deployment_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.listAppsV1beta1DeploymentForAllNamespaces") listAppsV1beta1DeploymentForAllNamespaces

> list or watch objects of kind Deployment


```php
function listAppsV1beta1DeploymentForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 178;
$watch = true;

$result = $appsV1beta1->listAppsV1beta1DeploymentForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_apps_v1beta1_namespaced_deployment"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.listAppsV1beta1NamespacedDeployment") listAppsV1beta1NamespacedDeployment

> list or watch objects of kind Deployment


```php
function listAppsV1beta1NamespacedDeployment(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 178;
$watch = true;
$pretty = 'pretty';

$result = $appsV1beta1->listAppsV1beta1NamespacedDeployment($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_apps_v1beta1_namespaced_deployment"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.createAppsV1beta1NamespacedDeployment") createAppsV1beta1NamespacedDeployment

> create a Deployment


```php
function createAppsV1beta1NamespacedDeployment(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAppsV1beta1Deployment();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $appsV1beta1->createAppsV1beta1NamespacedDeployment($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_apps_v1beta1_collection_namespaced_deployment"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.deleteAppsV1beta1CollectionNamespacedDeployment") deleteAppsV1beta1CollectionNamespacedDeployment

> delete collection of Deployment


```php
function deleteAppsV1beta1CollectionNamespacedDeployment(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 178;
$watch = true;
$pretty = 'pretty';

$result = $appsV1beta1->deleteAppsV1beta1CollectionNamespacedDeployment($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_apps_v1beta1_namespaced_deployment"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.getReadAppsV1beta1NamespacedDeployment") getReadAppsV1beta1NamespacedDeployment

> read the specified Deployment


```php
function getReadAppsV1beta1NamespacedDeployment(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Deployment |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = true;
$export = true;
$pretty = 'pretty';

$result = $appsV1beta1->getReadAppsV1beta1NamespacedDeployment($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_apps_v1beta1_namespaced_deployment"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.updateReplaceAppsV1beta1NamespacedDeployment") updateReplaceAppsV1beta1NamespacedDeployment

> replace the specified Deployment


```php
function updateReplaceAppsV1beta1NamespacedDeployment(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Deployment |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAppsV1beta1Deployment();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $appsV1beta1->updateReplaceAppsV1beta1NamespacedDeployment($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_apps_v1beta1_namespaced_deployment"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.deleteAppsV1beta1NamespacedDeployment") deleteAppsV1beta1NamespacedDeployment

> delete a Deployment


```php
function deleteAppsV1beta1NamespacedDeployment(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Deployment |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 15;
$orphanDependents = false;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $appsV1beta1->deleteAppsV1beta1NamespacedDeployment($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_apps_v1beta1_namespaced_deployment"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.patchAppsV1beta1NamespacedDeployment") patchAppsV1beta1NamespacedDeployment

> partially update the specified Deployment


```php
function patchAppsV1beta1NamespacedDeployment(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Deployment |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $appsV1beta1->patchAppsV1beta1NamespacedDeployment($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_apps_v1beta1_namespaced_deployment_rollback_rollback"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.createAppsV1beta1NamespacedDeploymentRollbackRollback") createAppsV1beta1NamespacedDeploymentRollbackRollback

> create rollback of a DeploymentRollback


```php
function createAppsV1beta1NamespacedDeploymentRollbackRollback(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the DeploymentRollback |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAppsV1beta1DeploymentRollback();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $appsV1beta1->createAppsV1beta1NamespacedDeploymentRollbackRollback($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_apps_v1beta1_namespaced_scale_scale"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.getReadAppsV1beta1NamespacedScaleScale") getReadAppsV1beta1NamespacedScaleScale

> read scale of the specified Scale


```php
function getReadAppsV1beta1NamespacedScaleScale(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Scale |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $appsV1beta1->getReadAppsV1beta1NamespacedScaleScale($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_apps_v1beta1_namespaced_scale_scale"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.updateReplaceAppsV1beta1NamespacedScaleScale") updateReplaceAppsV1beta1NamespacedScaleScale

> replace scale of the specified Scale


```php
function updateReplaceAppsV1beta1NamespacedScaleScale(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Scale |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAppsV1beta1Scale();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $appsV1beta1->updateReplaceAppsV1beta1NamespacedScaleScale($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_apps_v1beta1_namespaced_scale_scale"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.patchAppsV1beta1NamespacedScaleScale") patchAppsV1beta1NamespacedScaleScale

> partially update scale of the specified Scale


```php
function patchAppsV1beta1NamespacedScaleScale(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Scale |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $appsV1beta1->patchAppsV1beta1NamespacedScaleScale($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_apps_v1beta1_namespaced_deployment_status"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.getReadAppsV1beta1NamespacedDeploymentStatus") getReadAppsV1beta1NamespacedDeploymentStatus

> read status of the specified Deployment


```php
function getReadAppsV1beta1NamespacedDeploymentStatus(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Deployment |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $appsV1beta1->getReadAppsV1beta1NamespacedDeploymentStatus($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_apps_v1beta1_namespaced_deployment_status"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.updateReplaceAppsV1beta1NamespacedDeploymentStatus") updateReplaceAppsV1beta1NamespacedDeploymentStatus

> replace status of the specified Deployment


```php
function updateReplaceAppsV1beta1NamespacedDeploymentStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Deployment |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAppsV1beta1Deployment();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $appsV1beta1->updateReplaceAppsV1beta1NamespacedDeploymentStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_apps_v1beta1_namespaced_deployment_status"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.patchAppsV1beta1NamespacedDeploymentStatus") patchAppsV1beta1NamespacedDeploymentStatus

> partially update status of the specified Deployment


```php
function patchAppsV1beta1NamespacedDeploymentStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Deployment |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $appsV1beta1->patchAppsV1beta1NamespacedDeploymentStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_apps_v1beta1_namespaced_stateful_set"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.listAppsV1beta1NamespacedStatefulSet") listAppsV1beta1NamespacedStatefulSet

> list or watch objects of kind StatefulSet


```php
function listAppsV1beta1NamespacedStatefulSet(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 15;
$watch = false;
$pretty = 'pretty';

$result = $appsV1beta1->listAppsV1beta1NamespacedStatefulSet($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_apps_v1beta1_namespaced_stateful_set"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.createAppsV1beta1NamespacedStatefulSet") createAppsV1beta1NamespacedStatefulSet

> create a StatefulSet


```php
function createAppsV1beta1NamespacedStatefulSet(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAppsV1beta1StatefulSet();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $appsV1beta1->createAppsV1beta1NamespacedStatefulSet($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_apps_v1beta1_collection_namespaced_stateful_set"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.deleteAppsV1beta1CollectionNamespacedStatefulSet") deleteAppsV1beta1CollectionNamespacedStatefulSet

> delete collection of StatefulSet


```php
function deleteAppsV1beta1CollectionNamespacedStatefulSet(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 15;
$watch = false;
$pretty = 'pretty';

$result = $appsV1beta1->deleteAppsV1beta1CollectionNamespacedStatefulSet($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_apps_v1beta1_namespaced_stateful_set"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.getReadAppsV1beta1NamespacedStatefulSet") getReadAppsV1beta1NamespacedStatefulSet

> read the specified StatefulSet


```php
function getReadAppsV1beta1NamespacedStatefulSet(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the StatefulSet |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = false;
$export = false;
$pretty = 'pretty';

$result = $appsV1beta1->getReadAppsV1beta1NamespacedStatefulSet($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_apps_v1beta1_namespaced_stateful_set"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.updateReplaceAppsV1beta1NamespacedStatefulSet") updateReplaceAppsV1beta1NamespacedStatefulSet

> replace the specified StatefulSet


```php
function updateReplaceAppsV1beta1NamespacedStatefulSet(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the StatefulSet |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAppsV1beta1StatefulSet();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $appsV1beta1->updateReplaceAppsV1beta1NamespacedStatefulSet($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_apps_v1beta1_namespaced_stateful_set"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.deleteAppsV1beta1NamespacedStatefulSet") deleteAppsV1beta1NamespacedStatefulSet

> delete a StatefulSet


```php
function deleteAppsV1beta1NamespacedStatefulSet(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the StatefulSet |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 106;
$orphanDependents = false;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $appsV1beta1->deleteAppsV1beta1NamespacedStatefulSet($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_apps_v1beta1_namespaced_stateful_set"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.patchAppsV1beta1NamespacedStatefulSet") patchAppsV1beta1NamespacedStatefulSet

> partially update the specified StatefulSet


```php
function patchAppsV1beta1NamespacedStatefulSet(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the StatefulSet |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $appsV1beta1->patchAppsV1beta1NamespacedStatefulSet($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_apps_v1beta1_namespaced_stateful_set_status"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.getReadAppsV1beta1NamespacedStatefulSetStatus") getReadAppsV1beta1NamespacedStatefulSetStatus

> read status of the specified StatefulSet


```php
function getReadAppsV1beta1NamespacedStatefulSetStatus(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the StatefulSet |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $appsV1beta1->getReadAppsV1beta1NamespacedStatefulSetStatus($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_apps_v1beta1_namespaced_stateful_set_status"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.updateReplaceAppsV1beta1NamespacedStatefulSetStatus") updateReplaceAppsV1beta1NamespacedStatefulSetStatus

> replace status of the specified StatefulSet


```php
function updateReplaceAppsV1beta1NamespacedStatefulSetStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the StatefulSet |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAppsV1beta1StatefulSet();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $appsV1beta1->updateReplaceAppsV1beta1NamespacedStatefulSetStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_apps_v1beta1_namespaced_stateful_set_status"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.patchAppsV1beta1NamespacedStatefulSetStatus") patchAppsV1beta1NamespacedStatefulSetStatus

> partially update status of the specified StatefulSet


```php
function patchAppsV1beta1NamespacedStatefulSetStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the StatefulSet |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $appsV1beta1->patchAppsV1beta1NamespacedStatefulSetStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_apps_v1beta1_stateful_set_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.listAppsV1beta1StatefulSetForAllNamespaces") listAppsV1beta1StatefulSetForAllNamespaces

> list or watch objects of kind StatefulSet


```php
function listAppsV1beta1StatefulSetForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 106;
$watch = false;

$result = $appsV1beta1->listAppsV1beta1StatefulSetForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_apps_v1beta1_deployment_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.getWatchAppsV1beta1DeploymentListForAllNamespaces") getWatchAppsV1beta1DeploymentListForAllNamespaces

> watch individual changes to a list of Deployment


```php
function getWatchAppsV1beta1DeploymentListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 106;
$watch = false;

$result = $appsV1beta1->getWatchAppsV1beta1DeploymentListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_apps_v1beta1_namespaced_deployment_list"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.getWatchAppsV1beta1NamespacedDeploymentList") getWatchAppsV1beta1NamespacedDeploymentList

> watch individual changes to a list of Deployment


```php
function getWatchAppsV1beta1NamespacedDeploymentList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 106;
$watch = false;

$result = $appsV1beta1->getWatchAppsV1beta1NamespacedDeploymentList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_apps_v1beta1_namespaced_deployment"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.getWatchAppsV1beta1NamespacedDeployment") getWatchAppsV1beta1NamespacedDeployment

> watch changes to an object of kind Deployment


```php
function getWatchAppsV1beta1NamespacedDeployment(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Deployment |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 106;
$watch = false;

$result = $appsV1beta1->getWatchAppsV1beta1NamespacedDeployment($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_apps_v1beta1_namespaced_stateful_set_list"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.getWatchAppsV1beta1NamespacedStatefulSetList") getWatchAppsV1beta1NamespacedStatefulSetList

> watch individual changes to a list of StatefulSet


```php
function getWatchAppsV1beta1NamespacedStatefulSetList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 106;
$watch = false;

$result = $appsV1beta1->getWatchAppsV1beta1NamespacedStatefulSetList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_apps_v1beta1_namespaced_stateful_set"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.getWatchAppsV1beta1NamespacedStatefulSet") getWatchAppsV1beta1NamespacedStatefulSet

> watch changes to an object of kind StatefulSet


```php
function getWatchAppsV1beta1NamespacedStatefulSet(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the StatefulSet |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 106;
$watch = false;

$result = $appsV1beta1->getWatchAppsV1beta1NamespacedStatefulSet($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_apps_v1beta1_stateful_set_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".AppsV1beta1Controller.getWatchAppsV1beta1StatefulSetListForAllNamespaces") getWatchAppsV1beta1StatefulSetListForAllNamespaces

> watch individual changes to a list of StatefulSet


```php
function getWatchAppsV1beta1StatefulSetListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 106;
$watch = false;

$result = $appsV1beta1->getWatchAppsV1beta1StatefulSetListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="authentication_controller"></a>![Class: ](https://apidocs.io/img/class.png ".AuthenticationController") AuthenticationController

### Get singleton instance

The singleton instance of the ``` AuthenticationController ``` class can be accessed from the API Client.

```php
$authentication = $client->getAuthentication();
```

### <a name="get_authentication_api_group"></a>![Method: ](https://apidocs.io/img/method.png ".AuthenticationController.getAuthenticationAPIGroup") getAuthenticationAPIGroup

> get information of a group


```php
function getAuthenticationAPIGroup()
```

#### Example Usage

```php

$result = $authentication->getAuthenticationAPIGroup();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="authentication_v1_controller"></a>![Class: ](https://apidocs.io/img/class.png ".AuthenticationV1Controller") AuthenticationV1Controller

### Get singleton instance

The singleton instance of the ``` AuthenticationV1Controller ``` class can be accessed from the API Client.

```php
$authenticationV1 = $client->getAuthenticationV1();
```

### <a name="get_authentication_v1_api_resources"></a>![Method: ](https://apidocs.io/img/method.png ".AuthenticationV1Controller.getAuthenticationV1APIResources") getAuthenticationV1APIResources

> get available resources


```php
function getAuthenticationV1APIResources()
```

#### Example Usage

```php

$result = $authenticationV1->getAuthenticationV1APIResources();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_authentication_v1_token_review"></a>![Method: ](https://apidocs.io/img/method.png ".AuthenticationV1Controller.createAuthenticationV1TokenReview") createAuthenticationV1TokenReview

> create a TokenReview


```php
function createAuthenticationV1TokenReview(
        $body,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAuthenticationV1TokenReview();
$pretty = 'pretty';

$result = $authenticationV1->createAuthenticationV1TokenReview($body, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="authentication_v1beta1_controller"></a>![Class: ](https://apidocs.io/img/class.png ".AuthenticationV1beta1Controller") AuthenticationV1beta1Controller

### Get singleton instance

The singleton instance of the ``` AuthenticationV1beta1Controller ``` class can be accessed from the API Client.

```php
$authenticationV1beta1 = $client->getAuthenticationV1beta1();
```

### <a name="get_authentication_v1beta1_api_resources"></a>![Method: ](https://apidocs.io/img/method.png ".AuthenticationV1beta1Controller.getAuthenticationV1beta1APIResources") getAuthenticationV1beta1APIResources

> get available resources


```php
function getAuthenticationV1beta1APIResources()
```

#### Example Usage

```php

$result = $authenticationV1beta1->getAuthenticationV1beta1APIResources();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_authentication_v1beta1_token_review"></a>![Method: ](https://apidocs.io/img/method.png ".AuthenticationV1beta1Controller.createAuthenticationV1beta1TokenReview") createAuthenticationV1beta1TokenReview

> create a TokenReview


```php
function createAuthenticationV1beta1TokenReview(
        $body,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAuthenticationV1TokenReview();
$pretty = 'pretty';

$result = $authenticationV1beta1->createAuthenticationV1beta1TokenReview($body, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="authorization_controller"></a>![Class: ](https://apidocs.io/img/class.png ".AuthorizationController") AuthorizationController

### Get singleton instance

The singleton instance of the ``` AuthorizationController ``` class can be accessed from the API Client.

```php
$authorization = $client->getAuthorization();
```

### <a name="get_authorization_api_group"></a>![Method: ](https://apidocs.io/img/method.png ".AuthorizationController.getAuthorizationAPIGroup") getAuthorizationAPIGroup

> get information of a group


```php
function getAuthorizationAPIGroup()
```

#### Example Usage

```php

$result = $authorization->getAuthorizationAPIGroup();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="authorization_v1_controller"></a>![Class: ](https://apidocs.io/img/class.png ".AuthorizationV1Controller") AuthorizationV1Controller

### Get singleton instance

The singleton instance of the ``` AuthorizationV1Controller ``` class can be accessed from the API Client.

```php
$authorizationV1 = $client->getAuthorizationV1();
```

### <a name="get_authorization_v1_api_resources"></a>![Method: ](https://apidocs.io/img/method.png ".AuthorizationV1Controller.getAuthorizationV1APIResources") getAuthorizationV1APIResources

> get available resources


```php
function getAuthorizationV1APIResources()
```

#### Example Usage

```php

$result = $authorizationV1->getAuthorizationV1APIResources();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_authorization_v1_namespaced_local_subject_access_review"></a>![Method: ](https://apidocs.io/img/method.png ".AuthorizationV1Controller.createAuthorizationV1NamespacedLocalSubjectAccessReview") createAuthorizationV1NamespacedLocalSubjectAccessReview

> create a LocalSubjectAccessReview


```php
function createAuthorizationV1NamespacedLocalSubjectAccessReview(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAuthorizationV1LocalSubjectAccessReview();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $authorizationV1->createAuthorizationV1NamespacedLocalSubjectAccessReview($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_authorization_v1_self_subject_access_review"></a>![Method: ](https://apidocs.io/img/method.png ".AuthorizationV1Controller.createAuthorizationV1SelfSubjectAccessReview") createAuthorizationV1SelfSubjectAccessReview

> create a SelfSubjectAccessReview


```php
function createAuthorizationV1SelfSubjectAccessReview(
        $body,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAuthorizationV1SelfSubjectAccessReview();
$pretty = 'pretty';

$result = $authorizationV1->createAuthorizationV1SelfSubjectAccessReview($body, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_authorization_v1_subject_access_review"></a>![Method: ](https://apidocs.io/img/method.png ".AuthorizationV1Controller.createAuthorizationV1SubjectAccessReview") createAuthorizationV1SubjectAccessReview

> create a SubjectAccessReview


```php
function createAuthorizationV1SubjectAccessReview(
        $body,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAuthorizationV1LocalSubjectAccessReview();
$pretty = 'pretty';

$result = $authorizationV1->createAuthorizationV1SubjectAccessReview($body, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="authorization_v1beta1_controller"></a>![Class: ](https://apidocs.io/img/class.png ".AuthorizationV1beta1Controller") AuthorizationV1beta1Controller

### Get singleton instance

The singleton instance of the ``` AuthorizationV1beta1Controller ``` class can be accessed from the API Client.

```php
$authorizationV1beta1 = $client->getAuthorizationV1beta1();
```

### <a name="get_authorization_v1beta1_api_resources"></a>![Method: ](https://apidocs.io/img/method.png ".AuthorizationV1beta1Controller.getAuthorizationV1beta1APIResources") getAuthorizationV1beta1APIResources

> get available resources


```php
function getAuthorizationV1beta1APIResources()
```

#### Example Usage

```php

$result = $authorizationV1beta1->getAuthorizationV1beta1APIResources();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_authorization_v1beta1_namespaced_local_subject_access_review"></a>![Method: ](https://apidocs.io/img/method.png ".AuthorizationV1beta1Controller.createAuthorizationV1beta1NamespacedLocalSubjectAccessReview") createAuthorizationV1beta1NamespacedLocalSubjectAccessReview

> create a LocalSubjectAccessReview


```php
function createAuthorizationV1beta1NamespacedLocalSubjectAccessReview(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAuthorizationV1beta1LocalSubjectAccessReview();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $authorizationV1beta1->createAuthorizationV1beta1NamespacedLocalSubjectAccessReview($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_authorization_v1beta1_self_subject_access_review"></a>![Method: ](https://apidocs.io/img/method.png ".AuthorizationV1beta1Controller.createAuthorizationV1beta1SelfSubjectAccessReview") createAuthorizationV1beta1SelfSubjectAccessReview

> create a SelfSubjectAccessReview


```php
function createAuthorizationV1beta1SelfSubjectAccessReview(
        $body,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAuthorizationV1SelfSubjectAccessReview();
$pretty = 'pretty';

$result = $authorizationV1beta1->createAuthorizationV1beta1SelfSubjectAccessReview($body, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_authorization_v1beta1_subject_access_review"></a>![Method: ](https://apidocs.io/img/method.png ".AuthorizationV1beta1Controller.createAuthorizationV1beta1SubjectAccessReview") createAuthorizationV1beta1SubjectAccessReview

> create a SubjectAccessReview


```php
function createAuthorizationV1beta1SubjectAccessReview(
        $body,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAuthorizationV1beta1LocalSubjectAccessReview();
$pretty = 'pretty';

$result = $authorizationV1beta1->createAuthorizationV1beta1SubjectAccessReview($body, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="autoscaling_controller"></a>![Class: ](https://apidocs.io/img/class.png ".AutoscalingController") AutoscalingController

### Get singleton instance

The singleton instance of the ``` AutoscalingController ``` class can be accessed from the API Client.

```php
$autoscaling = $client->getAutoscaling();
```

### <a name="get_autoscaling_api_group"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingController.getAutoscalingAPIGroup") getAutoscalingAPIGroup

> get information of a group


```php
function getAutoscalingAPIGroup()
```

#### Example Usage

```php

$result = $autoscaling->getAutoscalingAPIGroup();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="autoscaling_v1_controller"></a>![Class: ](https://apidocs.io/img/class.png ".AutoscalingV1Controller") AutoscalingV1Controller

### Get singleton instance

The singleton instance of the ``` AutoscalingV1Controller ``` class can be accessed from the API Client.

```php
$autoscalingV1 = $client->getAutoscalingV1();
```

### <a name="get_autoscaling_v1_api_resources"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV1Controller.getAutoscalingV1APIResources") getAutoscalingV1APIResources

> get available resources


```php
function getAutoscalingV1APIResources()
```

#### Example Usage

```php

$result = $autoscalingV1->getAutoscalingV1APIResources();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_autoscaling_v1_horizontal_pod_autoscaler_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV1Controller.listAutoscalingV1HorizontalPodAutoscalerForAllNamespaces") listAutoscalingV1HorizontalPodAutoscalerForAllNamespaces

> list or watch objects of kind HorizontalPodAutoscaler


```php
function listAutoscalingV1HorizontalPodAutoscalerForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 65;
$watch = false;

$result = $autoscalingV1->listAutoscalingV1HorizontalPodAutoscalerForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_autoscaling_v1_namespaced_horizontal_pod_autoscaler"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV1Controller.listAutoscalingV1NamespacedHorizontalPodAutoscaler") listAutoscalingV1NamespacedHorizontalPodAutoscaler

> list or watch objects of kind HorizontalPodAutoscaler


```php
function listAutoscalingV1NamespacedHorizontalPodAutoscaler(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 65;
$watch = false;
$pretty = 'pretty';

$result = $autoscalingV1->listAutoscalingV1NamespacedHorizontalPodAutoscaler($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_autoscaling_v1_namespaced_horizontal_pod_autoscaler"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV1Controller.createAutoscalingV1NamespacedHorizontalPodAutoscaler") createAutoscalingV1NamespacedHorizontalPodAutoscaler

> create a HorizontalPodAutoscaler


```php
function createAutoscalingV1NamespacedHorizontalPodAutoscaler(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAutoscalingV1HorizontalPodAutoscaler();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $autoscalingV1->createAutoscalingV1NamespacedHorizontalPodAutoscaler($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_autoscaling_v1_collection_namespaced_horizontal_pod_autoscaler"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV1Controller.deleteAutoscalingV1CollectionNamespacedHorizontalPodAutoscaler") deleteAutoscalingV1CollectionNamespacedHorizontalPodAutoscaler

> delete collection of HorizontalPodAutoscaler


```php
function deleteAutoscalingV1CollectionNamespacedHorizontalPodAutoscaler(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 65;
$watch = false;
$pretty = 'pretty';

$result = $autoscalingV1->deleteAutoscalingV1CollectionNamespacedHorizontalPodAutoscaler($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_autoscaling_v1_namespaced_horizontal_pod_autoscaler"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV1Controller.getReadAutoscalingV1NamespacedHorizontalPodAutoscaler") getReadAutoscalingV1NamespacedHorizontalPodAutoscaler

> read the specified HorizontalPodAutoscaler


```php
function getReadAutoscalingV1NamespacedHorizontalPodAutoscaler(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the HorizontalPodAutoscaler |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = false;
$export = false;
$pretty = 'pretty';

$result = $autoscalingV1->getReadAutoscalingV1NamespacedHorizontalPodAutoscaler($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_autoscaling_v1_namespaced_horizontal_pod_autoscaler"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV1Controller.updateReplaceAutoscalingV1NamespacedHorizontalPodAutoscaler") updateReplaceAutoscalingV1NamespacedHorizontalPodAutoscaler

> replace the specified HorizontalPodAutoscaler


```php
function updateReplaceAutoscalingV1NamespacedHorizontalPodAutoscaler(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the HorizontalPodAutoscaler |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAutoscalingV1HorizontalPodAutoscaler();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $autoscalingV1->updateReplaceAutoscalingV1NamespacedHorizontalPodAutoscaler($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_autoscaling_v1_namespaced_horizontal_pod_autoscaler"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV1Controller.deleteAutoscalingV1NamespacedHorizontalPodAutoscaler") deleteAutoscalingV1NamespacedHorizontalPodAutoscaler

> delete a HorizontalPodAutoscaler


```php
function deleteAutoscalingV1NamespacedHorizontalPodAutoscaler(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the HorizontalPodAutoscaler |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 65;
$orphanDependents = false;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $autoscalingV1->deleteAutoscalingV1NamespacedHorizontalPodAutoscaler($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_autoscaling_v1_namespaced_horizontal_pod_autoscaler"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV1Controller.patchAutoscalingV1NamespacedHorizontalPodAutoscaler") patchAutoscalingV1NamespacedHorizontalPodAutoscaler

> partially update the specified HorizontalPodAutoscaler


```php
function patchAutoscalingV1NamespacedHorizontalPodAutoscaler(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the HorizontalPodAutoscaler |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $autoscalingV1->patchAutoscalingV1NamespacedHorizontalPodAutoscaler($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_autoscaling_v1_namespaced_horizontal_pod_autoscaler_status"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV1Controller.getReadAutoscalingV1NamespacedHorizontalPodAutoscalerStatus") getReadAutoscalingV1NamespacedHorizontalPodAutoscalerStatus

> read status of the specified HorizontalPodAutoscaler


```php
function getReadAutoscalingV1NamespacedHorizontalPodAutoscalerStatus(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the HorizontalPodAutoscaler |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $autoscalingV1->getReadAutoscalingV1NamespacedHorizontalPodAutoscalerStatus($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_autoscaling_v1_namespaced_horizontal_pod_autoscaler_status"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV1Controller.updateReplaceAutoscalingV1NamespacedHorizontalPodAutoscalerStatus") updateReplaceAutoscalingV1NamespacedHorizontalPodAutoscalerStatus

> replace status of the specified HorizontalPodAutoscaler


```php
function updateReplaceAutoscalingV1NamespacedHorizontalPodAutoscalerStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the HorizontalPodAutoscaler |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAutoscalingV1HorizontalPodAutoscaler();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $autoscalingV1->updateReplaceAutoscalingV1NamespacedHorizontalPodAutoscalerStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_autoscaling_v1_namespaced_horizontal_pod_autoscaler_status"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV1Controller.patchAutoscalingV1NamespacedHorizontalPodAutoscalerStatus") patchAutoscalingV1NamespacedHorizontalPodAutoscalerStatus

> partially update status of the specified HorizontalPodAutoscaler


```php
function patchAutoscalingV1NamespacedHorizontalPodAutoscalerStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the HorizontalPodAutoscaler |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $autoscalingV1->patchAutoscalingV1NamespacedHorizontalPodAutoscalerStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_autoscaling_v1_horizontal_pod_autoscaler_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV1Controller.getWatchAutoscalingV1HorizontalPodAutoscalerListForAllNamespaces") getWatchAutoscalingV1HorizontalPodAutoscalerListForAllNamespaces

> watch individual changes to a list of HorizontalPodAutoscaler


```php
function getWatchAutoscalingV1HorizontalPodAutoscalerListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 156;
$watch = true;

$result = $autoscalingV1->getWatchAutoscalingV1HorizontalPodAutoscalerListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_autoscaling_v1_namespaced_horizontal_pod_autoscaler_list"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV1Controller.getWatchAutoscalingV1NamespacedHorizontalPodAutoscalerList") getWatchAutoscalingV1NamespacedHorizontalPodAutoscalerList

> watch individual changes to a list of HorizontalPodAutoscaler


```php
function getWatchAutoscalingV1NamespacedHorizontalPodAutoscalerList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 156;
$watch = true;

$result = $autoscalingV1->getWatchAutoscalingV1NamespacedHorizontalPodAutoscalerList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_autoscaling_v1_namespaced_horizontal_pod_autoscaler"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV1Controller.getWatchAutoscalingV1NamespacedHorizontalPodAutoscaler") getWatchAutoscalingV1NamespacedHorizontalPodAutoscaler

> watch changes to an object of kind HorizontalPodAutoscaler


```php
function getWatchAutoscalingV1NamespacedHorizontalPodAutoscaler(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the HorizontalPodAutoscaler |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 156;
$watch = true;

$result = $autoscalingV1->getWatchAutoscalingV1NamespacedHorizontalPodAutoscaler($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="autoscaling_v2alpha1_controller"></a>![Class: ](https://apidocs.io/img/class.png ".AutoscalingV2alpha1Controller") AutoscalingV2alpha1Controller

### Get singleton instance

The singleton instance of the ``` AutoscalingV2alpha1Controller ``` class can be accessed from the API Client.

```php
$autoscalingV2alpha1 = $client->getAutoscalingV2alpha1();
```

### <a name="get_autoscaling_v2alpha1_api_resources"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV2alpha1Controller.getAutoscalingV2alpha1APIResources") getAutoscalingV2alpha1APIResources

> get available resources


```php
function getAutoscalingV2alpha1APIResources()
```

#### Example Usage

```php

$result = $autoscalingV2alpha1->getAutoscalingV2alpha1APIResources();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_autoscaling_v2alpha1_horizontal_pod_autoscaler_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV2alpha1Controller.listAutoscalingV2alpha1HorizontalPodAutoscalerForAllNamespaces") listAutoscalingV2alpha1HorizontalPodAutoscalerForAllNamespaces

> list or watch objects of kind HorizontalPodAutoscaler


```php
function listAutoscalingV2alpha1HorizontalPodAutoscalerForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 156;
$watch = true;

$result = $autoscalingV2alpha1->listAutoscalingV2alpha1HorizontalPodAutoscalerForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_autoscaling_v2alpha1_namespaced_horizontal_pod_autoscaler"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV2alpha1Controller.listAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler") listAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler

> list or watch objects of kind HorizontalPodAutoscaler


```php
function listAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 156;
$watch = true;
$pretty = 'pretty';

$result = $autoscalingV2alpha1->listAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_autoscaling_v2alpha1_namespaced_horizontal_pod_autoscaler"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV2alpha1Controller.createAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler") createAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler

> create a HorizontalPodAutoscaler


```php
function createAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAutoscalingV2alpha1HorizontalPodAutoscaler();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $autoscalingV2alpha1->createAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_autoscaling_v2alpha1_collection_namespaced_horizontal_pod_autoscaler"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV2alpha1Controller.deleteAutoscalingV2alpha1CollectionNamespacedHorizontalPodAutoscaler") deleteAutoscalingV2alpha1CollectionNamespacedHorizontalPodAutoscaler

> delete collection of HorizontalPodAutoscaler


```php
function deleteAutoscalingV2alpha1CollectionNamespacedHorizontalPodAutoscaler(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 156;
$watch = true;
$pretty = 'pretty';

$result = $autoscalingV2alpha1->deleteAutoscalingV2alpha1CollectionNamespacedHorizontalPodAutoscaler($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_autoscaling_v2alpha1_namespaced_horizontal_pod_autoscaler"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV2alpha1Controller.getReadAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler") getReadAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler

> read the specified HorizontalPodAutoscaler


```php
function getReadAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the HorizontalPodAutoscaler |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = true;
$export = true;
$pretty = 'pretty';

$result = $autoscalingV2alpha1->getReadAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_autoscaling_v2alpha1_namespaced_horizontal_pod_autoscaler"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV2alpha1Controller.updateReplaceAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler") updateReplaceAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler

> replace the specified HorizontalPodAutoscaler


```php
function updateReplaceAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the HorizontalPodAutoscaler |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAutoscalingV2alpha1HorizontalPodAutoscaler();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $autoscalingV2alpha1->updateReplaceAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_autoscaling_v2alpha1_namespaced_horizontal_pod_autoscaler"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV2alpha1Controller.deleteAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler") deleteAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler

> delete a HorizontalPodAutoscaler


```php
function deleteAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the HorizontalPodAutoscaler |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 248;
$orphanDependents = true;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $autoscalingV2alpha1->deleteAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_autoscaling_v2alpha1_namespaced_horizontal_pod_autoscaler"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV2alpha1Controller.patchAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler") patchAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler

> partially update the specified HorizontalPodAutoscaler


```php
function patchAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the HorizontalPodAutoscaler |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $autoscalingV2alpha1->patchAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_autoscaling_v2alpha1_namespaced_horizontal_pod_autoscaler_status"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV2alpha1Controller.getReadAutoscalingV2alpha1NamespacedHorizontalPodAutoscalerStatus") getReadAutoscalingV2alpha1NamespacedHorizontalPodAutoscalerStatus

> read status of the specified HorizontalPodAutoscaler


```php
function getReadAutoscalingV2alpha1NamespacedHorizontalPodAutoscalerStatus(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the HorizontalPodAutoscaler |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $autoscalingV2alpha1->getReadAutoscalingV2alpha1NamespacedHorizontalPodAutoscalerStatus($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_autoscaling_v2alpha1_namespaced_horizontal_pod_autoscaler_status"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV2alpha1Controller.updateReplaceAutoscalingV2alpha1NamespacedHorizontalPodAutoscalerStatus") updateReplaceAutoscalingV2alpha1NamespacedHorizontalPodAutoscalerStatus

> replace status of the specified HorizontalPodAutoscaler


```php
function updateReplaceAutoscalingV2alpha1NamespacedHorizontalPodAutoscalerStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the HorizontalPodAutoscaler |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAutoscalingV2alpha1HorizontalPodAutoscaler();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $autoscalingV2alpha1->updateReplaceAutoscalingV2alpha1NamespacedHorizontalPodAutoscalerStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_autoscaling_v2alpha1_namespaced_horizontal_pod_autoscaler_status"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV2alpha1Controller.patchAutoscalingV2alpha1NamespacedHorizontalPodAutoscalerStatus") patchAutoscalingV2alpha1NamespacedHorizontalPodAutoscalerStatus

> partially update status of the specified HorizontalPodAutoscaler


```php
function patchAutoscalingV2alpha1NamespacedHorizontalPodAutoscalerStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the HorizontalPodAutoscaler |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $autoscalingV2alpha1->patchAutoscalingV2alpha1NamespacedHorizontalPodAutoscalerStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_autoscaling_v2alpha1_horizontal_pod_autoscaler_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV2alpha1Controller.getWatchAutoscalingV2alpha1HorizontalPodAutoscalerListForAllNamespaces") getWatchAutoscalingV2alpha1HorizontalPodAutoscalerListForAllNamespaces

> watch individual changes to a list of HorizontalPodAutoscaler


```php
function getWatchAutoscalingV2alpha1HorizontalPodAutoscalerListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 248;
$watch = true;

$result = $autoscalingV2alpha1->getWatchAutoscalingV2alpha1HorizontalPodAutoscalerListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_autoscaling_v2alpha1_namespaced_horizontal_pod_autoscaler_list"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV2alpha1Controller.getWatchAutoscalingV2alpha1NamespacedHorizontalPodAutoscalerList") getWatchAutoscalingV2alpha1NamespacedHorizontalPodAutoscalerList

> watch individual changes to a list of HorizontalPodAutoscaler


```php
function getWatchAutoscalingV2alpha1NamespacedHorizontalPodAutoscalerList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 248;
$watch = true;

$result = $autoscalingV2alpha1->getWatchAutoscalingV2alpha1NamespacedHorizontalPodAutoscalerList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_autoscaling_v2alpha1_namespaced_horizontal_pod_autoscaler"></a>![Method: ](https://apidocs.io/img/method.png ".AutoscalingV2alpha1Controller.getWatchAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler") getWatchAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler

> watch changes to an object of kind HorizontalPodAutoscaler


```php
function getWatchAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the HorizontalPodAutoscaler |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 248;
$watch = true;

$result = $autoscalingV2alpha1->getWatchAutoscalingV2alpha1NamespacedHorizontalPodAutoscaler($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="batch_controller"></a>![Class: ](https://apidocs.io/img/class.png ".BatchController") BatchController

### Get singleton instance

The singleton instance of the ``` BatchController ``` class can be accessed from the API Client.

```php
$batch = $client->getBatch();
```

### <a name="get_batch_api_group"></a>![Method: ](https://apidocs.io/img/method.png ".BatchController.getBatchAPIGroup") getBatchAPIGroup

> get information of a group


```php
function getBatchAPIGroup()
```

#### Example Usage

```php

$result = $batch->getBatchAPIGroup();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="batch_v1_controller"></a>![Class: ](https://apidocs.io/img/class.png ".BatchV1Controller") BatchV1Controller

### Get singleton instance

The singleton instance of the ``` BatchV1Controller ``` class can be accessed from the API Client.

```php
$batchV1 = $client->getBatchV1();
```

### <a name="get_batch_v1_api_resources"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV1Controller.getBatchV1APIResources") getBatchV1APIResources

> get available resources


```php
function getBatchV1APIResources()
```

#### Example Usage

```php

$result = $batchV1->getBatchV1APIResources();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_batch_v1_job_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV1Controller.listBatchV1JobForAllNamespaces") listBatchV1JobForAllNamespaces

> list or watch objects of kind Job


```php
function listBatchV1JobForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 248;
$watch = true;

$result = $batchV1->listBatchV1JobForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_batch_v1_namespaced_job"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV1Controller.listBatchV1NamespacedJob") listBatchV1NamespacedJob

> list or watch objects of kind Job


```php
function listBatchV1NamespacedJob(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 248;
$watch = true;
$pretty = 'pretty';

$result = $batchV1->listBatchV1NamespacedJob($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_batch_v1_namespaced_job"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV1Controller.createBatchV1NamespacedJob") createBatchV1NamespacedJob

> create a Job


```php
function createBatchV1NamespacedJob(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisBatchV1Job();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $batchV1->createBatchV1NamespacedJob($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_batch_v1_collection_namespaced_job"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV1Controller.deleteBatchV1CollectionNamespacedJob") deleteBatchV1CollectionNamespacedJob

> delete collection of Job


```php
function deleteBatchV1CollectionNamespacedJob(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 206;
$watch = true;
$pretty = 'pretty';

$result = $batchV1->deleteBatchV1CollectionNamespacedJob($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_batch_v1_namespaced_job"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV1Controller.getReadBatchV1NamespacedJob") getReadBatchV1NamespacedJob

> read the specified Job


```php
function getReadBatchV1NamespacedJob(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Job |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = true;
$export = true;
$pretty = 'pretty';

$result = $batchV1->getReadBatchV1NamespacedJob($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_batch_v1_namespaced_job"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV1Controller.updateReplaceBatchV1NamespacedJob") updateReplaceBatchV1NamespacedJob

> replace the specified Job


```php
function updateReplaceBatchV1NamespacedJob(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Job |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisBatchV1Job();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $batchV1->updateReplaceBatchV1NamespacedJob($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_batch_v1_namespaced_job"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV1Controller.deleteBatchV1NamespacedJob") deleteBatchV1NamespacedJob

> delete a Job


```php
function deleteBatchV1NamespacedJob(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Job |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 206;
$orphanDependents = true;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $batchV1->deleteBatchV1NamespacedJob($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_batch_v1_namespaced_job"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV1Controller.patchBatchV1NamespacedJob") patchBatchV1NamespacedJob

> partially update the specified Job


```php
function patchBatchV1NamespacedJob(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Job |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $batchV1->patchBatchV1NamespacedJob($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_batch_v1_namespaced_job_status"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV1Controller.getReadBatchV1NamespacedJobStatus") getReadBatchV1NamespacedJobStatus

> read status of the specified Job


```php
function getReadBatchV1NamespacedJobStatus(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Job |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $batchV1->getReadBatchV1NamespacedJobStatus($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_batch_v1_namespaced_job_status"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV1Controller.updateReplaceBatchV1NamespacedJobStatus") updateReplaceBatchV1NamespacedJobStatus

> replace status of the specified Job


```php
function updateReplaceBatchV1NamespacedJobStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Job |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisBatchV1Job();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $batchV1->updateReplaceBatchV1NamespacedJobStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_batch_v1_namespaced_job_status"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV1Controller.patchBatchV1NamespacedJobStatus") patchBatchV1NamespacedJobStatus

> partially update status of the specified Job


```php
function patchBatchV1NamespacedJobStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Job |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $batchV1->patchBatchV1NamespacedJobStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_batch_v1_job_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV1Controller.getWatchBatchV1JobListForAllNamespaces") getWatchBatchV1JobListForAllNamespaces

> watch individual changes to a list of Job


```php
function getWatchBatchV1JobListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 206;
$watch = true;

$result = $batchV1->getWatchBatchV1JobListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_batch_v1_namespaced_job_list"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV1Controller.getWatchBatchV1NamespacedJobList") getWatchBatchV1NamespacedJobList

> watch individual changes to a list of Job


```php
function getWatchBatchV1NamespacedJobList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 206;
$watch = true;

$result = $batchV1->getWatchBatchV1NamespacedJobList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_batch_v1_namespaced_job"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV1Controller.getWatchBatchV1NamespacedJob") getWatchBatchV1NamespacedJob

> watch changes to an object of kind Job


```php
function getWatchBatchV1NamespacedJob(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Job |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 206;
$watch = true;

$result = $batchV1->getWatchBatchV1NamespacedJob($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="batch_v2alpha1_controller"></a>![Class: ](https://apidocs.io/img/class.png ".BatchV2alpha1Controller") BatchV2alpha1Controller

### Get singleton instance

The singleton instance of the ``` BatchV2alpha1Controller ``` class can be accessed from the API Client.

```php
$batchV2alpha1 = $client->getBatchV2alpha1();
```

### <a name="get_batch_v2alpha1_api_resources"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.getBatchV2alpha1APIResources") getBatchV2alpha1APIResources

> get available resources


```php
function getBatchV2alpha1APIResources()
```

#### Example Usage

```php

$result = $batchV2alpha1->getBatchV2alpha1APIResources();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_batch_v2alpha1_cron_job_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.listBatchV2alpha1CronJobForAllNamespaces") listBatchV2alpha1CronJobForAllNamespaces

> list or watch objects of kind CronJob


```php
function listBatchV2alpha1CronJobForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 206;
$watch = true;

$result = $batchV2alpha1->listBatchV2alpha1CronJobForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_batch_v2alpha1_namespaced_cron_job"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.listBatchV2alpha1NamespacedCronJob") listBatchV2alpha1NamespacedCronJob

> list or watch objects of kind CronJob


```php
function listBatchV2alpha1NamespacedCronJob(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 206;
$watch = true;
$pretty = 'pretty';

$result = $batchV2alpha1->listBatchV2alpha1NamespacedCronJob($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_batch_v2alpha1_namespaced_cron_job"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.createBatchV2alpha1NamespacedCronJob") createBatchV2alpha1NamespacedCronJob

> create a CronJob


```php
function createBatchV2alpha1NamespacedCronJob(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisBatchV2alpha1CronJob();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $batchV2alpha1->createBatchV2alpha1NamespacedCronJob($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_batch_v2alpha1_collection_namespaced_cron_job"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.deleteBatchV2alpha1CollectionNamespacedCronJob") deleteBatchV2alpha1CollectionNamespacedCronJob

> delete collection of CronJob


```php
function deleteBatchV2alpha1CollectionNamespacedCronJob(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 42;
$watch = false;
$pretty = 'pretty';

$result = $batchV2alpha1->deleteBatchV2alpha1CollectionNamespacedCronJob($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_batch_v2alpha1_namespaced_cron_job"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.getReadBatchV2alpha1NamespacedCronJob") getReadBatchV2alpha1NamespacedCronJob

> read the specified CronJob


```php
function getReadBatchV2alpha1NamespacedCronJob(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the CronJob |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = false;
$export = false;
$pretty = 'pretty';

$result = $batchV2alpha1->getReadBatchV2alpha1NamespacedCronJob($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_batch_v2alpha1_namespaced_cron_job"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.updateReplaceBatchV2alpha1NamespacedCronJob") updateReplaceBatchV2alpha1NamespacedCronJob

> replace the specified CronJob


```php
function updateReplaceBatchV2alpha1NamespacedCronJob(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the CronJob |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisBatchV2alpha1CronJob();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $batchV2alpha1->updateReplaceBatchV2alpha1NamespacedCronJob($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_batch_v2alpha1_namespaced_cron_job"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.deleteBatchV2alpha1NamespacedCronJob") deleteBatchV2alpha1NamespacedCronJob

> delete a CronJob


```php
function deleteBatchV2alpha1NamespacedCronJob(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the CronJob |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 42;
$orphanDependents = false;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $batchV2alpha1->deleteBatchV2alpha1NamespacedCronJob($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_batch_v2alpha1_namespaced_cron_job"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.patchBatchV2alpha1NamespacedCronJob") patchBatchV2alpha1NamespacedCronJob

> partially update the specified CronJob


```php
function patchBatchV2alpha1NamespacedCronJob(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the CronJob |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $batchV2alpha1->patchBatchV2alpha1NamespacedCronJob($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_batch_v2alpha1_namespaced_cron_job_status"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.getReadBatchV2alpha1NamespacedCronJobStatus") getReadBatchV2alpha1NamespacedCronJobStatus

> read status of the specified CronJob


```php
function getReadBatchV2alpha1NamespacedCronJobStatus(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the CronJob |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $batchV2alpha1->getReadBatchV2alpha1NamespacedCronJobStatus($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_batch_v2alpha1_namespaced_cron_job_status"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.updateReplaceBatchV2alpha1NamespacedCronJobStatus") updateReplaceBatchV2alpha1NamespacedCronJobStatus

> replace status of the specified CronJob


```php
function updateReplaceBatchV2alpha1NamespacedCronJobStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the CronJob |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisBatchV2alpha1CronJob();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $batchV2alpha1->updateReplaceBatchV2alpha1NamespacedCronJobStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_batch_v2alpha1_namespaced_cron_job_status"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.patchBatchV2alpha1NamespacedCronJobStatus") patchBatchV2alpha1NamespacedCronJobStatus

> partially update status of the specified CronJob


```php
function patchBatchV2alpha1NamespacedCronJobStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the CronJob |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $batchV2alpha1->patchBatchV2alpha1NamespacedCronJobStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_batch_v2alpha1_namespaced_scheduled_job"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.listBatchV2alpha1NamespacedScheduledJob") listBatchV2alpha1NamespacedScheduledJob

> list or watch objects of kind ScheduledJob


```php
function listBatchV2alpha1NamespacedScheduledJob(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 42;
$watch = false;
$pretty = 'pretty';

$result = $batchV2alpha1->listBatchV2alpha1NamespacedScheduledJob($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_batch_v2alpha1_namespaced_scheduled_job"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.createBatchV2alpha1NamespacedScheduledJob") createBatchV2alpha1NamespacedScheduledJob

> create a ScheduledJob


```php
function createBatchV2alpha1NamespacedScheduledJob(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisBatchV2alpha1CronJob();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $batchV2alpha1->createBatchV2alpha1NamespacedScheduledJob($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_batch_v2alpha1_collection_namespaced_scheduled_job"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.deleteBatchV2alpha1CollectionNamespacedScheduledJob") deleteBatchV2alpha1CollectionNamespacedScheduledJob

> delete collection of ScheduledJob


```php
function deleteBatchV2alpha1CollectionNamespacedScheduledJob(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 42;
$watch = false;
$pretty = 'pretty';

$result = $batchV2alpha1->deleteBatchV2alpha1CollectionNamespacedScheduledJob($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_batch_v2alpha1_namespaced_scheduled_job"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.getReadBatchV2alpha1NamespacedScheduledJob") getReadBatchV2alpha1NamespacedScheduledJob

> read the specified ScheduledJob


```php
function getReadBatchV2alpha1NamespacedScheduledJob(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ScheduledJob |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = false;
$export = false;
$pretty = 'pretty';

$result = $batchV2alpha1->getReadBatchV2alpha1NamespacedScheduledJob($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_batch_v2alpha1_namespaced_scheduled_job"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.updateReplaceBatchV2alpha1NamespacedScheduledJob") updateReplaceBatchV2alpha1NamespacedScheduledJob

> replace the specified ScheduledJob


```php
function updateReplaceBatchV2alpha1NamespacedScheduledJob(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ScheduledJob |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisBatchV2alpha1CronJob();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $batchV2alpha1->updateReplaceBatchV2alpha1NamespacedScheduledJob($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_batch_v2alpha1_namespaced_scheduled_job"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.deleteBatchV2alpha1NamespacedScheduledJob") deleteBatchV2alpha1NamespacedScheduledJob

> delete a ScheduledJob


```php
function deleteBatchV2alpha1NamespacedScheduledJob(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ScheduledJob |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 1;
$orphanDependents = false;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $batchV2alpha1->deleteBatchV2alpha1NamespacedScheduledJob($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_batch_v2alpha1_namespaced_scheduled_job"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.patchBatchV2alpha1NamespacedScheduledJob") patchBatchV2alpha1NamespacedScheduledJob

> partially update the specified ScheduledJob


```php
function patchBatchV2alpha1NamespacedScheduledJob(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ScheduledJob |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $batchV2alpha1->patchBatchV2alpha1NamespacedScheduledJob($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_batch_v2alpha1_namespaced_scheduled_job_status"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.getReadBatchV2alpha1NamespacedScheduledJobStatus") getReadBatchV2alpha1NamespacedScheduledJobStatus

> read status of the specified ScheduledJob


```php
function getReadBatchV2alpha1NamespacedScheduledJobStatus(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ScheduledJob |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $batchV2alpha1->getReadBatchV2alpha1NamespacedScheduledJobStatus($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_batch_v2alpha1_namespaced_scheduled_job_status"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.updateReplaceBatchV2alpha1NamespacedScheduledJobStatus") updateReplaceBatchV2alpha1NamespacedScheduledJobStatus

> replace status of the specified ScheduledJob


```php
function updateReplaceBatchV2alpha1NamespacedScheduledJobStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ScheduledJob |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisBatchV2alpha1CronJob();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $batchV2alpha1->updateReplaceBatchV2alpha1NamespacedScheduledJobStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_batch_v2alpha1_namespaced_scheduled_job_status"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.patchBatchV2alpha1NamespacedScheduledJobStatus") patchBatchV2alpha1NamespacedScheduledJobStatus

> partially update status of the specified ScheduledJob


```php
function patchBatchV2alpha1NamespacedScheduledJobStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ScheduledJob |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $batchV2alpha1->patchBatchV2alpha1NamespacedScheduledJobStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_batch_v2alpha1_scheduled_job_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.listBatchV2alpha1ScheduledJobForAllNamespaces") listBatchV2alpha1ScheduledJobForAllNamespaces

> list or watch objects of kind ScheduledJob


```php
function listBatchV2alpha1ScheduledJobForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 1;
$watch = false;

$result = $batchV2alpha1->listBatchV2alpha1ScheduledJobForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_batch_v2alpha1_cron_job_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.getWatchBatchV2alpha1CronJobListForAllNamespaces") getWatchBatchV2alpha1CronJobListForAllNamespaces

> watch individual changes to a list of CronJob


```php
function getWatchBatchV2alpha1CronJobListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 1;
$watch = false;

$result = $batchV2alpha1->getWatchBatchV2alpha1CronJobListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_batch_v2alpha1_namespaced_cron_job_list"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.getWatchBatchV2alpha1NamespacedCronJobList") getWatchBatchV2alpha1NamespacedCronJobList

> watch individual changes to a list of CronJob


```php
function getWatchBatchV2alpha1NamespacedCronJobList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 1;
$watch = false;

$result = $batchV2alpha1->getWatchBatchV2alpha1NamespacedCronJobList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_batch_v2alpha1_namespaced_cron_job"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.getWatchBatchV2alpha1NamespacedCronJob") getWatchBatchV2alpha1NamespacedCronJob

> watch changes to an object of kind CronJob


```php
function getWatchBatchV2alpha1NamespacedCronJob(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the CronJob |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 1;
$watch = false;

$result = $batchV2alpha1->getWatchBatchV2alpha1NamespacedCronJob($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_batch_v2alpha1_namespaced_scheduled_job_list"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.getWatchBatchV2alpha1NamespacedScheduledJobList") getWatchBatchV2alpha1NamespacedScheduledJobList

> watch individual changes to a list of ScheduledJob


```php
function getWatchBatchV2alpha1NamespacedScheduledJobList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 1;
$watch = false;

$result = $batchV2alpha1->getWatchBatchV2alpha1NamespacedScheduledJobList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_batch_v2alpha1_namespaced_scheduled_job"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.getWatchBatchV2alpha1NamespacedScheduledJob") getWatchBatchV2alpha1NamespacedScheduledJob

> watch changes to an object of kind ScheduledJob


```php
function getWatchBatchV2alpha1NamespacedScheduledJob(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ScheduledJob |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 1;
$watch = false;

$result = $batchV2alpha1->getWatchBatchV2alpha1NamespacedScheduledJob($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_batch_v2alpha1_scheduled_job_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".BatchV2alpha1Controller.getWatchBatchV2alpha1ScheduledJobListForAllNamespaces") getWatchBatchV2alpha1ScheduledJobListForAllNamespaces

> watch individual changes to a list of ScheduledJob


```php
function getWatchBatchV2alpha1ScheduledJobListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 1;
$watch = false;

$result = $batchV2alpha1->getWatchBatchV2alpha1ScheduledJobListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="certificates_controller"></a>![Class: ](https://apidocs.io/img/class.png ".CertificatesController") CertificatesController

### Get singleton instance

The singleton instance of the ``` CertificatesController ``` class can be accessed from the API Client.

```php
$certificates = $client->getCertificates();
```

### <a name="get_certificates_api_group"></a>![Method: ](https://apidocs.io/img/method.png ".CertificatesController.getCertificatesAPIGroup") getCertificatesAPIGroup

> get information of a group


```php
function getCertificatesAPIGroup()
```

#### Example Usage

```php

$result = $certificates->getCertificatesAPIGroup();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="certificates_v1beta1_controller"></a>![Class: ](https://apidocs.io/img/class.png ".CertificatesV1beta1Controller") CertificatesV1beta1Controller

### Get singleton instance

The singleton instance of the ``` CertificatesV1beta1Controller ``` class can be accessed from the API Client.

```php
$certificatesV1beta1 = $client->getCertificatesV1beta1();
```

### <a name="get_certificates_v1beta1_api_resources"></a>![Method: ](https://apidocs.io/img/method.png ".CertificatesV1beta1Controller.getCertificatesV1beta1APIResources") getCertificatesV1beta1APIResources

> get available resources


```php
function getCertificatesV1beta1APIResources()
```

#### Example Usage

```php

$result = $certificatesV1beta1->getCertificatesV1beta1APIResources();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_certificates_v1beta1_certificate_signing_request"></a>![Method: ](https://apidocs.io/img/method.png ".CertificatesV1beta1Controller.listCertificatesV1beta1CertificateSigningRequest") listCertificatesV1beta1CertificateSigningRequest

> list or watch objects of kind CertificateSigningRequest


```php
function listCertificatesV1beta1CertificateSigningRequest(
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 92;
$watch = false;
$pretty = 'pretty';

$result = $certificatesV1beta1->listCertificatesV1beta1CertificateSigningRequest($fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_certificates_v1beta1_certificate_signing_request"></a>![Method: ](https://apidocs.io/img/method.png ".CertificatesV1beta1Controller.createCertificatesV1beta1CertificateSigningRequest") createCertificatesV1beta1CertificateSigningRequest

> create a CertificateSigningRequest


```php
function createCertificatesV1beta1CertificateSigningRequest(
        $body,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisCertificatesV1beta1CertificateSigningRequest();
$pretty = 'pretty';

$result = $certificatesV1beta1->createCertificatesV1beta1CertificateSigningRequest($body, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_certificates_v1beta1_collection_certificate_signing_request"></a>![Method: ](https://apidocs.io/img/method.png ".CertificatesV1beta1Controller.deleteCertificatesV1beta1CollectionCertificateSigningRequest") deleteCertificatesV1beta1CollectionCertificateSigningRequest

> delete collection of CertificateSigningRequest


```php
function deleteCertificatesV1beta1CollectionCertificateSigningRequest(
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 92;
$watch = false;
$pretty = 'pretty';

$result = $certificatesV1beta1->deleteCertificatesV1beta1CollectionCertificateSigningRequest($fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_certificates_v1beta1_certificate_signing_request"></a>![Method: ](https://apidocs.io/img/method.png ".CertificatesV1beta1Controller.getReadCertificatesV1beta1CertificateSigningRequest") getReadCertificatesV1beta1CertificateSigningRequest

> read the specified CertificateSigningRequest


```php
function getReadCertificatesV1beta1CertificateSigningRequest(
        $name,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the CertificateSigningRequest |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$exact = false;
$export = false;
$pretty = 'pretty';

$result = $certificatesV1beta1->getReadCertificatesV1beta1CertificateSigningRequest($name, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_certificates_v1beta1_certificate_signing_request"></a>![Method: ](https://apidocs.io/img/method.png ".CertificatesV1beta1Controller.updateReplaceCertificatesV1beta1CertificateSigningRequest") updateReplaceCertificatesV1beta1CertificateSigningRequest

> replace the specified CertificateSigningRequest


```php
function updateReplaceCertificatesV1beta1CertificateSigningRequest(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the CertificateSigningRequest |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisCertificatesV1beta1CertificateSigningRequest();
$name = 'name';
$pretty = 'pretty';

$result = $certificatesV1beta1->updateReplaceCertificatesV1beta1CertificateSigningRequest($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_certificates_v1beta1_certificate_signing_request"></a>![Method: ](https://apidocs.io/img/method.png ".CertificatesV1beta1Controller.deleteCertificatesV1beta1CertificateSigningRequest") deleteCertificatesV1beta1CertificateSigningRequest

> delete a CertificateSigningRequest


```php
function deleteCertificatesV1beta1CertificateSigningRequest(
        $body,
        $name,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the CertificateSigningRequest |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$gracePeriodSeconds = 92;
$orphanDependents = false;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $certificatesV1beta1->deleteCertificatesV1beta1CertificateSigningRequest($body, $name, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_certificates_v1beta1_certificate_signing_request"></a>![Method: ](https://apidocs.io/img/method.png ".CertificatesV1beta1Controller.patchCertificatesV1beta1CertificateSigningRequest") patchCertificatesV1beta1CertificateSigningRequest

> partially update the specified CertificateSigningRequest


```php
function patchCertificatesV1beta1CertificateSigningRequest(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the CertificateSigningRequest |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$pretty = 'pretty';

$result = $certificatesV1beta1->patchCertificatesV1beta1CertificateSigningRequest($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_certificates_v1beta1_certificate_signing_request_approval"></a>![Method: ](https://apidocs.io/img/method.png ".CertificatesV1beta1Controller.updateReplaceCertificatesV1beta1CertificateSigningRequestApproval") updateReplaceCertificatesV1beta1CertificateSigningRequestApproval

> replace approval of the specified CertificateSigningRequest


```php
function updateReplaceCertificatesV1beta1CertificateSigningRequestApproval(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the CertificateSigningRequest |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisCertificatesV1beta1CertificateSigningRequest();
$name = 'name';
$pretty = 'pretty';

$result = $certificatesV1beta1->updateReplaceCertificatesV1beta1CertificateSigningRequestApproval($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_certificates_v1beta1_certificate_signing_request_status"></a>![Method: ](https://apidocs.io/img/method.png ".CertificatesV1beta1Controller.updateReplaceCertificatesV1beta1CertificateSigningRequestStatus") updateReplaceCertificatesV1beta1CertificateSigningRequestStatus

> replace status of the specified CertificateSigningRequest


```php
function updateReplaceCertificatesV1beta1CertificateSigningRequestStatus(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the CertificateSigningRequest |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisCertificatesV1beta1CertificateSigningRequest();
$name = 'name';
$pretty = 'pretty';

$result = $certificatesV1beta1->updateReplaceCertificatesV1beta1CertificateSigningRequestStatus($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_certificates_v1beta1_certificate_signing_request_list"></a>![Method: ](https://apidocs.io/img/method.png ".CertificatesV1beta1Controller.getWatchCertificatesV1beta1CertificateSigningRequestList") getWatchCertificatesV1beta1CertificateSigningRequestList

> watch individual changes to a list of CertificateSigningRequest


```php
function getWatchCertificatesV1beta1CertificateSigningRequestList(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 92;
$watch = false;

$result = $certificatesV1beta1->getWatchCertificatesV1beta1CertificateSigningRequestList($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_certificates_v1beta1_certificate_signing_request"></a>![Method: ](https://apidocs.io/img/method.png ".CertificatesV1beta1Controller.getWatchCertificatesV1beta1CertificateSigningRequest") getWatchCertificatesV1beta1CertificateSigningRequest

> watch changes to an object of kind CertificateSigningRequest


```php
function getWatchCertificatesV1beta1CertificateSigningRequest(
        $name,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the CertificateSigningRequest |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 92;
$watch = false;

$result = $certificatesV1beta1->getWatchCertificatesV1beta1CertificateSigningRequest($name, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="extensions_controller"></a>![Class: ](https://apidocs.io/img/class.png ".ExtensionsController") ExtensionsController

### Get singleton instance

The singleton instance of the ``` ExtensionsController ``` class can be accessed from the API Client.

```php
$extensions = $client->getExtensions();
```

### <a name="get_extensions_api_group"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsController.getExtensionsAPIGroup") getExtensionsAPIGroup

> get information of a group


```php
function getExtensionsAPIGroup()
```

#### Example Usage

```php

$result = $extensions->getExtensionsAPIGroup();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="extensions_v1beta1_controller"></a>![Class: ](https://apidocs.io/img/class.png ".ExtensionsV1beta1Controller") ExtensionsV1beta1Controller

### Get singleton instance

The singleton instance of the ``` ExtensionsV1beta1Controller ``` class can be accessed from the API Client.

```php
$extensionsV1beta1 = $client->getExtensionsV1beta1();
```

### <a name="get_extensions_v1beta1_api_resources"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getExtensionsV1beta1APIResources") getExtensionsV1beta1APIResources

> get available resources


```php
function getExtensionsV1beta1APIResources()
```

#### Example Usage

```php

$result = $extensionsV1beta1->getExtensionsV1beta1APIResources();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_extensions_v1beta1_daemon_set_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.listExtensionsV1beta1DaemonSetForAllNamespaces") listExtensionsV1beta1DaemonSetForAllNamespaces

> list or watch objects of kind DaemonSet


```php
function listExtensionsV1beta1DaemonSetForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 92;
$watch = false;

$result = $extensionsV1beta1->listExtensionsV1beta1DaemonSetForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_extensions_v1beta1_deployment_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.listExtensionsV1beta1DeploymentForAllNamespaces") listExtensionsV1beta1DeploymentForAllNamespaces

> list or watch objects of kind Deployment


```php
function listExtensionsV1beta1DeploymentForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 92;
$watch = true;

$result = $extensionsV1beta1->listExtensionsV1beta1DeploymentForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_extensions_v1beta1_ingress_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.listExtensionsV1beta1IngressForAllNamespaces") listExtensionsV1beta1IngressForAllNamespaces

> list or watch objects of kind Ingress


```php
function listExtensionsV1beta1IngressForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 184;
$watch = true;

$result = $extensionsV1beta1->listExtensionsV1beta1IngressForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_extensions_v1beta1_namespaced_daemon_set"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.listExtensionsV1beta1NamespacedDaemonSet") listExtensionsV1beta1NamespacedDaemonSet

> list or watch objects of kind DaemonSet


```php
function listExtensionsV1beta1NamespacedDaemonSet(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 184;
$watch = true;
$pretty = 'pretty';

$result = $extensionsV1beta1->listExtensionsV1beta1NamespacedDaemonSet($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_extensions_v1beta1_namespaced_daemon_set"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.createExtensionsV1beta1NamespacedDaemonSet") createExtensionsV1beta1NamespacedDaemonSet

> create a DaemonSet


```php
function createExtensionsV1beta1NamespacedDaemonSet(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisExtensionsV1beta1DaemonSet();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->createExtensionsV1beta1NamespacedDaemonSet($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_extensions_v1beta1_collection_namespaced_daemon_set"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.deleteExtensionsV1beta1CollectionNamespacedDaemonSet") deleteExtensionsV1beta1CollectionNamespacedDaemonSet

> delete collection of DaemonSet


```php
function deleteExtensionsV1beta1CollectionNamespacedDaemonSet(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 184;
$watch = true;
$pretty = 'pretty';

$result = $extensionsV1beta1->deleteExtensionsV1beta1CollectionNamespacedDaemonSet($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_extensions_v1beta1_namespaced_daemon_set"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getReadExtensionsV1beta1NamespacedDaemonSet") getReadExtensionsV1beta1NamespacedDaemonSet

> read the specified DaemonSet


```php
function getReadExtensionsV1beta1NamespacedDaemonSet(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the DaemonSet |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = true;
$export = true;
$pretty = 'pretty';

$result = $extensionsV1beta1->getReadExtensionsV1beta1NamespacedDaemonSet($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_extensions_v1beta1_namespaced_daemon_set"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.updateReplaceExtensionsV1beta1NamespacedDaemonSet") updateReplaceExtensionsV1beta1NamespacedDaemonSet

> replace the specified DaemonSet


```php
function updateReplaceExtensionsV1beta1NamespacedDaemonSet(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the DaemonSet |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisExtensionsV1beta1DaemonSet();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->updateReplaceExtensionsV1beta1NamespacedDaemonSet($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_extensions_v1beta1_namespaced_daemon_set"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.deleteExtensionsV1beta1NamespacedDaemonSet") deleteExtensionsV1beta1NamespacedDaemonSet

> delete a DaemonSet


```php
function deleteExtensionsV1beta1NamespacedDaemonSet(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the DaemonSet |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 184;
$orphanDependents = true;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $extensionsV1beta1->deleteExtensionsV1beta1NamespacedDaemonSet($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_extensions_v1beta1_namespaced_daemon_set"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.patchExtensionsV1beta1NamespacedDaemonSet") patchExtensionsV1beta1NamespacedDaemonSet

> partially update the specified DaemonSet


```php
function patchExtensionsV1beta1NamespacedDaemonSet(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the DaemonSet |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->patchExtensionsV1beta1NamespacedDaemonSet($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_extensions_v1beta1_namespaced_daemon_set_status"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getReadExtensionsV1beta1NamespacedDaemonSetStatus") getReadExtensionsV1beta1NamespacedDaemonSetStatus

> read status of the specified DaemonSet


```php
function getReadExtensionsV1beta1NamespacedDaemonSetStatus(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the DaemonSet |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->getReadExtensionsV1beta1NamespacedDaemonSetStatus($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_extensions_v1beta1_namespaced_daemon_set_status"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.updateReplaceExtensionsV1beta1NamespacedDaemonSetStatus") updateReplaceExtensionsV1beta1NamespacedDaemonSetStatus

> replace status of the specified DaemonSet


```php
function updateReplaceExtensionsV1beta1NamespacedDaemonSetStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the DaemonSet |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisExtensionsV1beta1DaemonSet();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->updateReplaceExtensionsV1beta1NamespacedDaemonSetStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_extensions_v1beta1_namespaced_daemon_set_status"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.patchExtensionsV1beta1NamespacedDaemonSetStatus") patchExtensionsV1beta1NamespacedDaemonSetStatus

> partially update status of the specified DaemonSet


```php
function patchExtensionsV1beta1NamespacedDaemonSetStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the DaemonSet |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->patchExtensionsV1beta1NamespacedDaemonSetStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_extensions_v1beta1_namespaced_deployment"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.listExtensionsV1beta1NamespacedDeployment") listExtensionsV1beta1NamespacedDeployment

> list or watch objects of kind Deployment


```php
function listExtensionsV1beta1NamespacedDeployment(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 184;
$watch = true;
$pretty = 'pretty';

$result = $extensionsV1beta1->listExtensionsV1beta1NamespacedDeployment($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_extensions_v1beta1_namespaced_deployment"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.createExtensionsV1beta1NamespacedDeployment") createExtensionsV1beta1NamespacedDeployment

> create a Deployment


```php
function createExtensionsV1beta1NamespacedDeployment(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAppsV1beta1Deployment();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->createExtensionsV1beta1NamespacedDeployment($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_extensions_v1beta1_collection_namespaced_deployment"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.deleteExtensionsV1beta1CollectionNamespacedDeployment") deleteExtensionsV1beta1CollectionNamespacedDeployment

> delete collection of Deployment


```php
function deleteExtensionsV1beta1CollectionNamespacedDeployment(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 142;
$watch = true;
$pretty = 'pretty';

$result = $extensionsV1beta1->deleteExtensionsV1beta1CollectionNamespacedDeployment($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_extensions_v1beta1_namespaced_deployment"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getReadExtensionsV1beta1NamespacedDeployment") getReadExtensionsV1beta1NamespacedDeployment

> read the specified Deployment


```php
function getReadExtensionsV1beta1NamespacedDeployment(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Deployment |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = true;
$export = true;
$pretty = 'pretty';

$result = $extensionsV1beta1->getReadExtensionsV1beta1NamespacedDeployment($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_extensions_v1beta1_namespaced_deployment"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.updateReplaceExtensionsV1beta1NamespacedDeployment") updateReplaceExtensionsV1beta1NamespacedDeployment

> replace the specified Deployment


```php
function updateReplaceExtensionsV1beta1NamespacedDeployment(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Deployment |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAppsV1beta1Deployment();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->updateReplaceExtensionsV1beta1NamespacedDeployment($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_extensions_v1beta1_namespaced_deployment"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.deleteExtensionsV1beta1NamespacedDeployment") deleteExtensionsV1beta1NamespacedDeployment

> delete a Deployment


```php
function deleteExtensionsV1beta1NamespacedDeployment(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Deployment |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 142;
$orphanDependents = true;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $extensionsV1beta1->deleteExtensionsV1beta1NamespacedDeployment($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_extensions_v1beta1_namespaced_deployment"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.patchExtensionsV1beta1NamespacedDeployment") patchExtensionsV1beta1NamespacedDeployment

> partially update the specified Deployment


```php
function patchExtensionsV1beta1NamespacedDeployment(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Deployment |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->patchExtensionsV1beta1NamespacedDeployment($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_extensions_v1beta1_namespaced_deployment_rollback_rollback"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.createExtensionsV1beta1NamespacedDeploymentRollbackRollback") createExtensionsV1beta1NamespacedDeploymentRollbackRollback

> create rollback of a DeploymentRollback


```php
function createExtensionsV1beta1NamespacedDeploymentRollbackRollback(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the DeploymentRollback |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAppsV1beta1DeploymentRollback();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->createExtensionsV1beta1NamespacedDeploymentRollbackRollback($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_extensions_v1beta1_namespaced_deployments_scale"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getReadExtensionsV1beta1NamespacedDeploymentsScale") getReadExtensionsV1beta1NamespacedDeploymentsScale

> read scale of the specified Scale


```php
function getReadExtensionsV1beta1NamespacedDeploymentsScale(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Scale |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->getReadExtensionsV1beta1NamespacedDeploymentsScale($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_extensions_v1beta1_namespaced_deployments_scale"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.updateReplaceExtensionsV1beta1NamespacedDeploymentsScale") updateReplaceExtensionsV1beta1NamespacedDeploymentsScale

> replace scale of the specified Scale


```php
function updateReplaceExtensionsV1beta1NamespacedDeploymentsScale(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Scale |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAppsV1beta1Scale();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->updateReplaceExtensionsV1beta1NamespacedDeploymentsScale($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_extensions_v1beta1_namespaced_deployments_scale"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.patchExtensionsV1beta1NamespacedDeploymentsScale") patchExtensionsV1beta1NamespacedDeploymentsScale

> partially update scale of the specified Scale


```php
function patchExtensionsV1beta1NamespacedDeploymentsScale(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Scale |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->patchExtensionsV1beta1NamespacedDeploymentsScale($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_extensions_v1beta1_namespaced_deployment_status"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getReadExtensionsV1beta1NamespacedDeploymentStatus") getReadExtensionsV1beta1NamespacedDeploymentStatus

> read status of the specified Deployment


```php
function getReadExtensionsV1beta1NamespacedDeploymentStatus(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Deployment |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->getReadExtensionsV1beta1NamespacedDeploymentStatus($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_extensions_v1beta1_namespaced_deployment_status"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.updateReplaceExtensionsV1beta1NamespacedDeploymentStatus") updateReplaceExtensionsV1beta1NamespacedDeploymentStatus

> replace status of the specified Deployment


```php
function updateReplaceExtensionsV1beta1NamespacedDeploymentStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Deployment |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAppsV1beta1Deployment();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->updateReplaceExtensionsV1beta1NamespacedDeploymentStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_extensions_v1beta1_namespaced_deployment_status"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.patchExtensionsV1beta1NamespacedDeploymentStatus") patchExtensionsV1beta1NamespacedDeploymentStatus

> partially update status of the specified Deployment


```php
function patchExtensionsV1beta1NamespacedDeploymentStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Deployment |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->patchExtensionsV1beta1NamespacedDeploymentStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_extensions_v1beta1_namespaced_ingress"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.listExtensionsV1beta1NamespacedIngress") listExtensionsV1beta1NamespacedIngress

> list or watch objects of kind Ingress


```php
function listExtensionsV1beta1NamespacedIngress(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 142;
$watch = true;
$pretty = 'pretty';

$result = $extensionsV1beta1->listExtensionsV1beta1NamespacedIngress($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_extensions_v1beta1_namespaced_ingress"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.createExtensionsV1beta1NamespacedIngress") createExtensionsV1beta1NamespacedIngress

> create an Ingress


```php
function createExtensionsV1beta1NamespacedIngress(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisExtensionsV1beta1Ingress();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->createExtensionsV1beta1NamespacedIngress($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_extensions_v1beta1_collection_namespaced_ingress"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.deleteExtensionsV1beta1CollectionNamespacedIngress") deleteExtensionsV1beta1CollectionNamespacedIngress

> delete collection of Ingress


```php
function deleteExtensionsV1beta1CollectionNamespacedIngress(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 142;
$watch = true;
$pretty = 'pretty';

$result = $extensionsV1beta1->deleteExtensionsV1beta1CollectionNamespacedIngress($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_extensions_v1beta1_namespaced_ingress"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getReadExtensionsV1beta1NamespacedIngress") getReadExtensionsV1beta1NamespacedIngress

> read the specified Ingress


```php
function getReadExtensionsV1beta1NamespacedIngress(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Ingress |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = true;
$export = true;
$pretty = 'pretty';

$result = $extensionsV1beta1->getReadExtensionsV1beta1NamespacedIngress($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_extensions_v1beta1_namespaced_ingress"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.updateReplaceExtensionsV1beta1NamespacedIngress") updateReplaceExtensionsV1beta1NamespacedIngress

> replace the specified Ingress


```php
function updateReplaceExtensionsV1beta1NamespacedIngress(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Ingress |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisExtensionsV1beta1Ingress();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->updateReplaceExtensionsV1beta1NamespacedIngress($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_extensions_v1beta1_namespaced_ingress"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.deleteExtensionsV1beta1NamespacedIngress") deleteExtensionsV1beta1NamespacedIngress

> delete an Ingress


```php
function deleteExtensionsV1beta1NamespacedIngress(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Ingress |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 233;
$orphanDependents = true;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $extensionsV1beta1->deleteExtensionsV1beta1NamespacedIngress($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_extensions_v1beta1_namespaced_ingress"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.patchExtensionsV1beta1NamespacedIngress") patchExtensionsV1beta1NamespacedIngress

> partially update the specified Ingress


```php
function patchExtensionsV1beta1NamespacedIngress(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Ingress |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->patchExtensionsV1beta1NamespacedIngress($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_extensions_v1beta1_namespaced_ingress_status"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getReadExtensionsV1beta1NamespacedIngressStatus") getReadExtensionsV1beta1NamespacedIngressStatus

> read status of the specified Ingress


```php
function getReadExtensionsV1beta1NamespacedIngressStatus(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Ingress |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->getReadExtensionsV1beta1NamespacedIngressStatus($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_extensions_v1beta1_namespaced_ingress_status"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.updateReplaceExtensionsV1beta1NamespacedIngressStatus") updateReplaceExtensionsV1beta1NamespacedIngressStatus

> replace status of the specified Ingress


```php
function updateReplaceExtensionsV1beta1NamespacedIngressStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Ingress |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisExtensionsV1beta1Ingress();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->updateReplaceExtensionsV1beta1NamespacedIngressStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_extensions_v1beta1_namespaced_ingress_status"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.patchExtensionsV1beta1NamespacedIngressStatus") patchExtensionsV1beta1NamespacedIngressStatus

> partially update status of the specified Ingress


```php
function patchExtensionsV1beta1NamespacedIngressStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Ingress |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->patchExtensionsV1beta1NamespacedIngressStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_extensions_v1beta1_namespaced_network_policy"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.listExtensionsV1beta1NamespacedNetworkPolicy") listExtensionsV1beta1NamespacedNetworkPolicy

> list or watch objects of kind NetworkPolicy


```php
function listExtensionsV1beta1NamespacedNetworkPolicy(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 233;
$watch = true;
$pretty = 'pretty';

$result = $extensionsV1beta1->listExtensionsV1beta1NamespacedNetworkPolicy($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_extensions_v1beta1_namespaced_network_policy"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.createExtensionsV1beta1NamespacedNetworkPolicy") createExtensionsV1beta1NamespacedNetworkPolicy

> create a NetworkPolicy


```php
function createExtensionsV1beta1NamespacedNetworkPolicy(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisExtensionsV1beta1NetworkPolicy();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->createExtensionsV1beta1NamespacedNetworkPolicy($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_extensions_v1beta1_collection_namespaced_network_policy"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.deleteExtensionsV1beta1CollectionNamespacedNetworkPolicy") deleteExtensionsV1beta1CollectionNamespacedNetworkPolicy

> delete collection of NetworkPolicy


```php
function deleteExtensionsV1beta1CollectionNamespacedNetworkPolicy(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 233;
$watch = true;
$pretty = 'pretty';

$result = $extensionsV1beta1->deleteExtensionsV1beta1CollectionNamespacedNetworkPolicy($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_extensions_v1beta1_namespaced_network_policy"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getReadExtensionsV1beta1NamespacedNetworkPolicy") getReadExtensionsV1beta1NamespacedNetworkPolicy

> read the specified NetworkPolicy


```php
function getReadExtensionsV1beta1NamespacedNetworkPolicy(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the NetworkPolicy |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = true;
$export = true;
$pretty = 'pretty';

$result = $extensionsV1beta1->getReadExtensionsV1beta1NamespacedNetworkPolicy($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_extensions_v1beta1_namespaced_network_policy"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.updateReplaceExtensionsV1beta1NamespacedNetworkPolicy") updateReplaceExtensionsV1beta1NamespacedNetworkPolicy

> replace the specified NetworkPolicy


```php
function updateReplaceExtensionsV1beta1NamespacedNetworkPolicy(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the NetworkPolicy |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisExtensionsV1beta1NetworkPolicy();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->updateReplaceExtensionsV1beta1NamespacedNetworkPolicy($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_extensions_v1beta1_namespaced_network_policy"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.deleteExtensionsV1beta1NamespacedNetworkPolicy") deleteExtensionsV1beta1NamespacedNetworkPolicy

> delete a NetworkPolicy


```php
function deleteExtensionsV1beta1NamespacedNetworkPolicy(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the NetworkPolicy |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 233;
$orphanDependents = true;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $extensionsV1beta1->deleteExtensionsV1beta1NamespacedNetworkPolicy($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_extensions_v1beta1_namespaced_network_policy"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.patchExtensionsV1beta1NamespacedNetworkPolicy") patchExtensionsV1beta1NamespacedNetworkPolicy

> partially update the specified NetworkPolicy


```php
function patchExtensionsV1beta1NamespacedNetworkPolicy(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the NetworkPolicy |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->patchExtensionsV1beta1NamespacedNetworkPolicy($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_extensions_v1beta1_namespaced_replica_set"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.listExtensionsV1beta1NamespacedReplicaSet") listExtensionsV1beta1NamespacedReplicaSet

> list or watch objects of kind ReplicaSet


```php
function listExtensionsV1beta1NamespacedReplicaSet(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 70;
$watch = false;
$pretty = 'pretty';

$result = $extensionsV1beta1->listExtensionsV1beta1NamespacedReplicaSet($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_extensions_v1beta1_namespaced_replica_set"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.createExtensionsV1beta1NamespacedReplicaSet") createExtensionsV1beta1NamespacedReplicaSet

> create a ReplicaSet


```php
function createExtensionsV1beta1NamespacedReplicaSet(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisExtensionsV1beta1ReplicaSet();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->createExtensionsV1beta1NamespacedReplicaSet($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_extensions_v1beta1_collection_namespaced_replica_set"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.deleteExtensionsV1beta1CollectionNamespacedReplicaSet") deleteExtensionsV1beta1CollectionNamespacedReplicaSet

> delete collection of ReplicaSet


```php
function deleteExtensionsV1beta1CollectionNamespacedReplicaSet(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 70;
$watch = false;
$pretty = 'pretty';

$result = $extensionsV1beta1->deleteExtensionsV1beta1CollectionNamespacedReplicaSet($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_extensions_v1beta1_namespaced_replica_set"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getReadExtensionsV1beta1NamespacedReplicaSet") getReadExtensionsV1beta1NamespacedReplicaSet

> read the specified ReplicaSet


```php
function getReadExtensionsV1beta1NamespacedReplicaSet(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ReplicaSet |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = false;
$export = false;
$pretty = 'pretty';

$result = $extensionsV1beta1->getReadExtensionsV1beta1NamespacedReplicaSet($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_extensions_v1beta1_namespaced_replica_set"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.updateReplaceExtensionsV1beta1NamespacedReplicaSet") updateReplaceExtensionsV1beta1NamespacedReplicaSet

> replace the specified ReplicaSet


```php
function updateReplaceExtensionsV1beta1NamespacedReplicaSet(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ReplicaSet |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisExtensionsV1beta1ReplicaSet();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->updateReplaceExtensionsV1beta1NamespacedReplicaSet($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_extensions_v1beta1_namespaced_replica_set"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.deleteExtensionsV1beta1NamespacedReplicaSet") deleteExtensionsV1beta1NamespacedReplicaSet

> delete a ReplicaSet


```php
function deleteExtensionsV1beta1NamespacedReplicaSet(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ReplicaSet |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 70;
$orphanDependents = false;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $extensionsV1beta1->deleteExtensionsV1beta1NamespacedReplicaSet($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_extensions_v1beta1_namespaced_replica_set"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.patchExtensionsV1beta1NamespacedReplicaSet") patchExtensionsV1beta1NamespacedReplicaSet

> partially update the specified ReplicaSet


```php
function patchExtensionsV1beta1NamespacedReplicaSet(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ReplicaSet |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->patchExtensionsV1beta1NamespacedReplicaSet($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_extensions_v1beta1_namespaced_replicasets_scale"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getReadExtensionsV1beta1NamespacedReplicasetsScale") getReadExtensionsV1beta1NamespacedReplicasetsScale

> read scale of the specified Scale


```php
function getReadExtensionsV1beta1NamespacedReplicasetsScale(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Scale |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->getReadExtensionsV1beta1NamespacedReplicasetsScale($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_extensions_v1beta1_namespaced_replicasets_scale"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.updateReplaceExtensionsV1beta1NamespacedReplicasetsScale") updateReplaceExtensionsV1beta1NamespacedReplicasetsScale

> replace scale of the specified Scale


```php
function updateReplaceExtensionsV1beta1NamespacedReplicasetsScale(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Scale |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAppsV1beta1Scale();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->updateReplaceExtensionsV1beta1NamespacedReplicasetsScale($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_extensions_v1beta1_namespaced_replicasets_scale"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.patchExtensionsV1beta1NamespacedReplicasetsScale") patchExtensionsV1beta1NamespacedReplicasetsScale

> partially update scale of the specified Scale


```php
function patchExtensionsV1beta1NamespacedReplicasetsScale(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Scale |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->patchExtensionsV1beta1NamespacedReplicasetsScale($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_extensions_v1beta1_namespaced_replica_set_status"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getReadExtensionsV1beta1NamespacedReplicaSetStatus") getReadExtensionsV1beta1NamespacedReplicaSetStatus

> read status of the specified ReplicaSet


```php
function getReadExtensionsV1beta1NamespacedReplicaSetStatus(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ReplicaSet |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->getReadExtensionsV1beta1NamespacedReplicaSetStatus($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_extensions_v1beta1_namespaced_replica_set_status"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.updateReplaceExtensionsV1beta1NamespacedReplicaSetStatus") updateReplaceExtensionsV1beta1NamespacedReplicaSetStatus

> replace status of the specified ReplicaSet


```php
function updateReplaceExtensionsV1beta1NamespacedReplicaSetStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ReplicaSet |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisExtensionsV1beta1ReplicaSet();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->updateReplaceExtensionsV1beta1NamespacedReplicaSetStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_extensions_v1beta1_namespaced_replica_set_status"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.patchExtensionsV1beta1NamespacedReplicaSetStatus") patchExtensionsV1beta1NamespacedReplicaSetStatus

> partially update status of the specified ReplicaSet


```php
function patchExtensionsV1beta1NamespacedReplicaSetStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ReplicaSet |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->patchExtensionsV1beta1NamespacedReplicaSetStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_extensions_v1beta1_namespaced_replicationcontrollers_scale"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getReadExtensionsV1beta1NamespacedReplicationcontrollersScale") getReadExtensionsV1beta1NamespacedReplicationcontrollersScale

> read scale of the specified Scale


```php
function getReadExtensionsV1beta1NamespacedReplicationcontrollersScale(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Scale |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->getReadExtensionsV1beta1NamespacedReplicationcontrollersScale($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_extensions_v1beta1_namespaced_replicationcontrollers_scale"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.updateReplaceExtensionsV1beta1NamespacedReplicationcontrollersScale") updateReplaceExtensionsV1beta1NamespacedReplicationcontrollersScale

> replace scale of the specified Scale


```php
function updateReplaceExtensionsV1beta1NamespacedReplicationcontrollersScale(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Scale |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisAppsV1beta1Scale();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->updateReplaceExtensionsV1beta1NamespacedReplicationcontrollersScale($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_extensions_v1beta1_namespaced_replicationcontrollers_scale"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.patchExtensionsV1beta1NamespacedReplicationcontrollersScale") patchExtensionsV1beta1NamespacedReplicationcontrollersScale

> partially update scale of the specified Scale


```php
function patchExtensionsV1beta1NamespacedReplicationcontrollersScale(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Scale |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $extensionsV1beta1->patchExtensionsV1beta1NamespacedReplicationcontrollersScale($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_extensions_v1beta1_network_policy_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.listExtensionsV1beta1NetworkPolicyForAllNamespaces") listExtensionsV1beta1NetworkPolicyForAllNamespaces

> list or watch objects of kind NetworkPolicy


```php
function listExtensionsV1beta1NetworkPolicyForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 28;
$watch = false;

$result = $extensionsV1beta1->listExtensionsV1beta1NetworkPolicyForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_extensions_v1beta1_pod_security_policy"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.listExtensionsV1beta1PodSecurityPolicy") listExtensionsV1beta1PodSecurityPolicy

> list or watch objects of kind PodSecurityPolicy


```php
function listExtensionsV1beta1PodSecurityPolicy(
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 28;
$watch = false;
$pretty = 'pretty';

$result = $extensionsV1beta1->listExtensionsV1beta1PodSecurityPolicy($fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_extensions_v1beta1_pod_security_policy"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.createExtensionsV1beta1PodSecurityPolicy") createExtensionsV1beta1PodSecurityPolicy

> create a PodSecurityPolicy


```php
function createExtensionsV1beta1PodSecurityPolicy(
        $body,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisExtensionsV1beta1PodSecurityPolicy();
$pretty = 'pretty';

$result = $extensionsV1beta1->createExtensionsV1beta1PodSecurityPolicy($body, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_extensions_v1beta1_collection_pod_security_policy"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.deleteExtensionsV1beta1CollectionPodSecurityPolicy") deleteExtensionsV1beta1CollectionPodSecurityPolicy

> delete collection of PodSecurityPolicy


```php
function deleteExtensionsV1beta1CollectionPodSecurityPolicy(
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 28;
$watch = false;
$pretty = 'pretty';

$result = $extensionsV1beta1->deleteExtensionsV1beta1CollectionPodSecurityPolicy($fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_extensions_v1beta1_pod_security_policy"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getReadExtensionsV1beta1PodSecurityPolicy") getReadExtensionsV1beta1PodSecurityPolicy

> read the specified PodSecurityPolicy


```php
function getReadExtensionsV1beta1PodSecurityPolicy(
        $name,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the PodSecurityPolicy |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$exact = false;
$export = false;
$pretty = 'pretty';

$result = $extensionsV1beta1->getReadExtensionsV1beta1PodSecurityPolicy($name, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_extensions_v1beta1_pod_security_policy"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.updateReplaceExtensionsV1beta1PodSecurityPolicy") updateReplaceExtensionsV1beta1PodSecurityPolicy

> replace the specified PodSecurityPolicy


```php
function updateReplaceExtensionsV1beta1PodSecurityPolicy(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the PodSecurityPolicy |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisExtensionsV1beta1PodSecurityPolicy();
$name = 'name';
$pretty = 'pretty';

$result = $extensionsV1beta1->updateReplaceExtensionsV1beta1PodSecurityPolicy($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_extensions_v1beta1_pod_security_policy"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.deleteExtensionsV1beta1PodSecurityPolicy") deleteExtensionsV1beta1PodSecurityPolicy

> delete a PodSecurityPolicy


```php
function deleteExtensionsV1beta1PodSecurityPolicy(
        $body,
        $name,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the PodSecurityPolicy |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$gracePeriodSeconds = 28;
$orphanDependents = false;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $extensionsV1beta1->deleteExtensionsV1beta1PodSecurityPolicy($body, $name, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_extensions_v1beta1_pod_security_policy"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.patchExtensionsV1beta1PodSecurityPolicy") patchExtensionsV1beta1PodSecurityPolicy

> partially update the specified PodSecurityPolicy


```php
function patchExtensionsV1beta1PodSecurityPolicy(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the PodSecurityPolicy |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$pretty = 'pretty';

$result = $extensionsV1beta1->patchExtensionsV1beta1PodSecurityPolicy($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_extensions_v1beta1_replica_set_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.listExtensionsV1beta1ReplicaSetForAllNamespaces") listExtensionsV1beta1ReplicaSetForAllNamespaces

> list or watch objects of kind ReplicaSet


```php
function listExtensionsV1beta1ReplicaSetForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 28;
$watch = false;

$result = $extensionsV1beta1->listExtensionsV1beta1ReplicaSetForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_extensions_v1beta1_third_party_resource"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.listExtensionsV1beta1ThirdPartyResource") listExtensionsV1beta1ThirdPartyResource

> list or watch objects of kind ThirdPartyResource


```php
function listExtensionsV1beta1ThirdPartyResource(
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 28;
$watch = false;
$pretty = 'pretty';

$result = $extensionsV1beta1->listExtensionsV1beta1ThirdPartyResource($fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_extensions_v1beta1_third_party_resource"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.createExtensionsV1beta1ThirdPartyResource") createExtensionsV1beta1ThirdPartyResource

> create a ThirdPartyResource


```php
function createExtensionsV1beta1ThirdPartyResource(
        $body,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisExtensionsV1beta1ThirdPartyResource();
$pretty = 'pretty';

$result = $extensionsV1beta1->createExtensionsV1beta1ThirdPartyResource($body, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_extensions_v1beta1_collection_third_party_resource"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.deleteExtensionsV1beta1CollectionThirdPartyResource") deleteExtensionsV1beta1CollectionThirdPartyResource

> delete collection of ThirdPartyResource


```php
function deleteExtensionsV1beta1CollectionThirdPartyResource(
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 28;
$watch = false;
$pretty = 'pretty';

$result = $extensionsV1beta1->deleteExtensionsV1beta1CollectionThirdPartyResource($fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_extensions_v1beta1_third_party_resource"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getReadExtensionsV1beta1ThirdPartyResource") getReadExtensionsV1beta1ThirdPartyResource

> read the specified ThirdPartyResource


```php
function getReadExtensionsV1beta1ThirdPartyResource(
        $name,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ThirdPartyResource |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$exact = false;
$export = false;
$pretty = 'pretty';

$result = $extensionsV1beta1->getReadExtensionsV1beta1ThirdPartyResource($name, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_extensions_v1beta1_third_party_resource"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.updateReplaceExtensionsV1beta1ThirdPartyResource") updateReplaceExtensionsV1beta1ThirdPartyResource

> replace the specified ThirdPartyResource


```php
function updateReplaceExtensionsV1beta1ThirdPartyResource(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ThirdPartyResource |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisExtensionsV1beta1ThirdPartyResource();
$name = 'name';
$pretty = 'pretty';

$result = $extensionsV1beta1->updateReplaceExtensionsV1beta1ThirdPartyResource($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_extensions_v1beta1_third_party_resource"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.deleteExtensionsV1beta1ThirdPartyResource") deleteExtensionsV1beta1ThirdPartyResource

> delete a ThirdPartyResource


```php
function deleteExtensionsV1beta1ThirdPartyResource(
        $body,
        $name,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ThirdPartyResource |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$gracePeriodSeconds = 120;
$orphanDependents = false;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $extensionsV1beta1->deleteExtensionsV1beta1ThirdPartyResource($body, $name, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_extensions_v1beta1_third_party_resource"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.patchExtensionsV1beta1ThirdPartyResource") patchExtensionsV1beta1ThirdPartyResource

> partially update the specified ThirdPartyResource


```php
function patchExtensionsV1beta1ThirdPartyResource(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ThirdPartyResource |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$pretty = 'pretty';

$result = $extensionsV1beta1->patchExtensionsV1beta1ThirdPartyResource($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_extensions_v1beta1_daemon_set_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getWatchExtensionsV1beta1DaemonSetListForAllNamespaces") getWatchExtensionsV1beta1DaemonSetListForAllNamespaces

> watch individual changes to a list of DaemonSet


```php
function getWatchExtensionsV1beta1DaemonSetListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 120;
$watch = false;

$result = $extensionsV1beta1->getWatchExtensionsV1beta1DaemonSetListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_extensions_v1beta1_deployment_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getWatchExtensionsV1beta1DeploymentListForAllNamespaces") getWatchExtensionsV1beta1DeploymentListForAllNamespaces

> watch individual changes to a list of Deployment


```php
function getWatchExtensionsV1beta1DeploymentListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 120;
$watch = false;

$result = $extensionsV1beta1->getWatchExtensionsV1beta1DeploymentListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_extensions_v1beta1_ingress_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getWatchExtensionsV1beta1IngressListForAllNamespaces") getWatchExtensionsV1beta1IngressListForAllNamespaces

> watch individual changes to a list of Ingress


```php
function getWatchExtensionsV1beta1IngressListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 120;
$watch = false;

$result = $extensionsV1beta1->getWatchExtensionsV1beta1IngressListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_extensions_v1beta1_namespaced_daemon_set_list"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getWatchExtensionsV1beta1NamespacedDaemonSetList") getWatchExtensionsV1beta1NamespacedDaemonSetList

> watch individual changes to a list of DaemonSet


```php
function getWatchExtensionsV1beta1NamespacedDaemonSetList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 120;
$watch = false;

$result = $extensionsV1beta1->getWatchExtensionsV1beta1NamespacedDaemonSetList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_extensions_v1beta1_namespaced_daemon_set"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getWatchExtensionsV1beta1NamespacedDaemonSet") getWatchExtensionsV1beta1NamespacedDaemonSet

> watch changes to an object of kind DaemonSet


```php
function getWatchExtensionsV1beta1NamespacedDaemonSet(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the DaemonSet |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 120;
$watch = false;

$result = $extensionsV1beta1->getWatchExtensionsV1beta1NamespacedDaemonSet($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_extensions_v1beta1_namespaced_deployment_list"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getWatchExtensionsV1beta1NamespacedDeploymentList") getWatchExtensionsV1beta1NamespacedDeploymentList

> watch individual changes to a list of Deployment


```php
function getWatchExtensionsV1beta1NamespacedDeploymentList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 120;
$watch = false;

$result = $extensionsV1beta1->getWatchExtensionsV1beta1NamespacedDeploymentList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_extensions_v1beta1_namespaced_deployment"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getWatchExtensionsV1beta1NamespacedDeployment") getWatchExtensionsV1beta1NamespacedDeployment

> watch changes to an object of kind Deployment


```php
function getWatchExtensionsV1beta1NamespacedDeployment(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Deployment |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 120;
$watch = false;

$result = $extensionsV1beta1->getWatchExtensionsV1beta1NamespacedDeployment($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_extensions_v1beta1_namespaced_ingress_list"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getWatchExtensionsV1beta1NamespacedIngressList") getWatchExtensionsV1beta1NamespacedIngressList

> watch individual changes to a list of Ingress


```php
function getWatchExtensionsV1beta1NamespacedIngressList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 78;
$watch = false;

$result = $extensionsV1beta1->getWatchExtensionsV1beta1NamespacedIngressList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_extensions_v1beta1_namespaced_ingress"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getWatchExtensionsV1beta1NamespacedIngress") getWatchExtensionsV1beta1NamespacedIngress

> watch changes to an object of kind Ingress


```php
function getWatchExtensionsV1beta1NamespacedIngress(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Ingress |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 78;
$watch = false;

$result = $extensionsV1beta1->getWatchExtensionsV1beta1NamespacedIngress($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_extensions_v1beta1_namespaced_network_policy_list"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getWatchExtensionsV1beta1NamespacedNetworkPolicyList") getWatchExtensionsV1beta1NamespacedNetworkPolicyList

> watch individual changes to a list of NetworkPolicy


```php
function getWatchExtensionsV1beta1NamespacedNetworkPolicyList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 78;
$watch = false;

$result = $extensionsV1beta1->getWatchExtensionsV1beta1NamespacedNetworkPolicyList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_extensions_v1beta1_namespaced_network_policy"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getWatchExtensionsV1beta1NamespacedNetworkPolicy") getWatchExtensionsV1beta1NamespacedNetworkPolicy

> watch changes to an object of kind NetworkPolicy


```php
function getWatchExtensionsV1beta1NamespacedNetworkPolicy(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the NetworkPolicy |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 78;
$watch = false;

$result = $extensionsV1beta1->getWatchExtensionsV1beta1NamespacedNetworkPolicy($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_extensions_v1beta1_namespaced_replica_set_list"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getWatchExtensionsV1beta1NamespacedReplicaSetList") getWatchExtensionsV1beta1NamespacedReplicaSetList

> watch individual changes to a list of ReplicaSet


```php
function getWatchExtensionsV1beta1NamespacedReplicaSetList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 78;
$watch = false;

$result = $extensionsV1beta1->getWatchExtensionsV1beta1NamespacedReplicaSetList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_extensions_v1beta1_namespaced_replica_set"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getWatchExtensionsV1beta1NamespacedReplicaSet") getWatchExtensionsV1beta1NamespacedReplicaSet

> watch changes to an object of kind ReplicaSet


```php
function getWatchExtensionsV1beta1NamespacedReplicaSet(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ReplicaSet |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 78;
$watch = false;

$result = $extensionsV1beta1->getWatchExtensionsV1beta1NamespacedReplicaSet($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_extensions_v1beta1_network_policy_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getWatchExtensionsV1beta1NetworkPolicyListForAllNamespaces") getWatchExtensionsV1beta1NetworkPolicyListForAllNamespaces

> watch individual changes to a list of NetworkPolicy


```php
function getWatchExtensionsV1beta1NetworkPolicyListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 78;
$watch = false;

$result = $extensionsV1beta1->getWatchExtensionsV1beta1NetworkPolicyListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_extensions_v1beta1_pod_security_policy_list"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getWatchExtensionsV1beta1PodSecurityPolicyList") getWatchExtensionsV1beta1PodSecurityPolicyList

> watch individual changes to a list of PodSecurityPolicy


```php
function getWatchExtensionsV1beta1PodSecurityPolicyList(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 78;
$watch = false;

$result = $extensionsV1beta1->getWatchExtensionsV1beta1PodSecurityPolicyList($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_extensions_v1beta1_pod_security_policy"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getWatchExtensionsV1beta1PodSecurityPolicy") getWatchExtensionsV1beta1PodSecurityPolicy

> watch changes to an object of kind PodSecurityPolicy


```php
function getWatchExtensionsV1beta1PodSecurityPolicy(
        $name,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the PodSecurityPolicy |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 78;
$watch = false;

$result = $extensionsV1beta1->getWatchExtensionsV1beta1PodSecurityPolicy($name, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_extensions_v1beta1_replica_set_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getWatchExtensionsV1beta1ReplicaSetListForAllNamespaces") getWatchExtensionsV1beta1ReplicaSetListForAllNamespaces

> watch individual changes to a list of ReplicaSet


```php
function getWatchExtensionsV1beta1ReplicaSetListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 78;
$watch = false;

$result = $extensionsV1beta1->getWatchExtensionsV1beta1ReplicaSetListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_extensions_v1beta1_third_party_resource_list"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getWatchExtensionsV1beta1ThirdPartyResourceList") getWatchExtensionsV1beta1ThirdPartyResourceList

> watch individual changes to a list of ThirdPartyResource


```php
function getWatchExtensionsV1beta1ThirdPartyResourceList(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 78;
$watch = false;

$result = $extensionsV1beta1->getWatchExtensionsV1beta1ThirdPartyResourceList($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_extensions_v1beta1_third_party_resource"></a>![Method: ](https://apidocs.io/img/method.png ".ExtensionsV1beta1Controller.getWatchExtensionsV1beta1ThirdPartyResource") getWatchExtensionsV1beta1ThirdPartyResource

> watch changes to an object of kind ThirdPartyResource


```php
function getWatchExtensionsV1beta1ThirdPartyResource(
        $name,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ThirdPartyResource |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 78;
$watch = false;

$result = $extensionsV1beta1->getWatchExtensionsV1beta1ThirdPartyResource($name, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="policy_controller"></a>![Class: ](https://apidocs.io/img/class.png ".PolicyController") PolicyController

### Get singleton instance

The singleton instance of the ``` PolicyController ``` class can be accessed from the API Client.

```php
$policy = $client->getPolicy();
```

### <a name="get_policy_api_group"></a>![Method: ](https://apidocs.io/img/method.png ".PolicyController.getPolicyAPIGroup") getPolicyAPIGroup

> get information of a group


```php
function getPolicyAPIGroup()
```

#### Example Usage

```php

$result = $policy->getPolicyAPIGroup();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="policy_v1beta1_controller"></a>![Class: ](https://apidocs.io/img/class.png ".PolicyV1beta1Controller") PolicyV1beta1Controller

### Get singleton instance

The singleton instance of the ``` PolicyV1beta1Controller ``` class can be accessed from the API Client.

```php
$policyV1beta1 = $client->getPolicyV1beta1();
```

### <a name="get_policy_v1beta1_api_resources"></a>![Method: ](https://apidocs.io/img/method.png ".PolicyV1beta1Controller.getPolicyV1beta1APIResources") getPolicyV1beta1APIResources

> get available resources


```php
function getPolicyV1beta1APIResources()
```

#### Example Usage

```php

$result = $policyV1beta1->getPolicyV1beta1APIResources();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_policy_v1beta1_namespaced_pod_disruption_budget"></a>![Method: ](https://apidocs.io/img/method.png ".PolicyV1beta1Controller.listPolicyV1beta1NamespacedPodDisruptionBudget") listPolicyV1beta1NamespacedPodDisruptionBudget

> list or watch objects of kind PodDisruptionBudget


```php
function listPolicyV1beta1NamespacedPodDisruptionBudget(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 169;
$watch = true;
$pretty = 'pretty';

$result = $policyV1beta1->listPolicyV1beta1NamespacedPodDisruptionBudget($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_policy_v1beta1_namespaced_pod_disruption_budget"></a>![Method: ](https://apidocs.io/img/method.png ".PolicyV1beta1Controller.createPolicyV1beta1NamespacedPodDisruptionBudget") createPolicyV1beta1NamespacedPodDisruptionBudget

> create a PodDisruptionBudget


```php
function createPolicyV1beta1NamespacedPodDisruptionBudget(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisPolicyV1beta1PodDisruptionBudget();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $policyV1beta1->createPolicyV1beta1NamespacedPodDisruptionBudget($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_policy_v1beta1_collection_namespaced_pod_disruption_budget"></a>![Method: ](https://apidocs.io/img/method.png ".PolicyV1beta1Controller.deletePolicyV1beta1CollectionNamespacedPodDisruptionBudget") deletePolicyV1beta1CollectionNamespacedPodDisruptionBudget

> delete collection of PodDisruptionBudget


```php
function deletePolicyV1beta1CollectionNamespacedPodDisruptionBudget(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 169;
$watch = true;
$pretty = 'pretty';

$result = $policyV1beta1->deletePolicyV1beta1CollectionNamespacedPodDisruptionBudget($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_policy_v1beta1_namespaced_pod_disruption_budget"></a>![Method: ](https://apidocs.io/img/method.png ".PolicyV1beta1Controller.getReadPolicyV1beta1NamespacedPodDisruptionBudget") getReadPolicyV1beta1NamespacedPodDisruptionBudget

> read the specified PodDisruptionBudget


```php
function getReadPolicyV1beta1NamespacedPodDisruptionBudget(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the PodDisruptionBudget |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = true;
$export = true;
$pretty = 'pretty';

$result = $policyV1beta1->getReadPolicyV1beta1NamespacedPodDisruptionBudget($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_policy_v1beta1_namespaced_pod_disruption_budget"></a>![Method: ](https://apidocs.io/img/method.png ".PolicyV1beta1Controller.updateReplacePolicyV1beta1NamespacedPodDisruptionBudget") updateReplacePolicyV1beta1NamespacedPodDisruptionBudget

> replace the specified PodDisruptionBudget


```php
function updateReplacePolicyV1beta1NamespacedPodDisruptionBudget(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the PodDisruptionBudget |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisPolicyV1beta1PodDisruptionBudget();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $policyV1beta1->updateReplacePolicyV1beta1NamespacedPodDisruptionBudget($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_policy_v1beta1_namespaced_pod_disruption_budget"></a>![Method: ](https://apidocs.io/img/method.png ".PolicyV1beta1Controller.deletePolicyV1beta1NamespacedPodDisruptionBudget") deletePolicyV1beta1NamespacedPodDisruptionBudget

> delete a PodDisruptionBudget


```php
function deletePolicyV1beta1NamespacedPodDisruptionBudget(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the PodDisruptionBudget |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 169;
$orphanDependents = true;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $policyV1beta1->deletePolicyV1beta1NamespacedPodDisruptionBudget($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_policy_v1beta1_namespaced_pod_disruption_budget"></a>![Method: ](https://apidocs.io/img/method.png ".PolicyV1beta1Controller.patchPolicyV1beta1NamespacedPodDisruptionBudget") patchPolicyV1beta1NamespacedPodDisruptionBudget

> partially update the specified PodDisruptionBudget


```php
function patchPolicyV1beta1NamespacedPodDisruptionBudget(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the PodDisruptionBudget |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $policyV1beta1->patchPolicyV1beta1NamespacedPodDisruptionBudget($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_policy_v1beta1_namespaced_pod_disruption_budget_status"></a>![Method: ](https://apidocs.io/img/method.png ".PolicyV1beta1Controller.getReadPolicyV1beta1NamespacedPodDisruptionBudgetStatus") getReadPolicyV1beta1NamespacedPodDisruptionBudgetStatus

> read status of the specified PodDisruptionBudget


```php
function getReadPolicyV1beta1NamespacedPodDisruptionBudgetStatus(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the PodDisruptionBudget |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $policyV1beta1->getReadPolicyV1beta1NamespacedPodDisruptionBudgetStatus($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_policy_v1beta1_namespaced_pod_disruption_budget_status"></a>![Method: ](https://apidocs.io/img/method.png ".PolicyV1beta1Controller.updateReplacePolicyV1beta1NamespacedPodDisruptionBudgetStatus") updateReplacePolicyV1beta1NamespacedPodDisruptionBudgetStatus

> replace status of the specified PodDisruptionBudget


```php
function updateReplacePolicyV1beta1NamespacedPodDisruptionBudgetStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the PodDisruptionBudget |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisPolicyV1beta1PodDisruptionBudget();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $policyV1beta1->updateReplacePolicyV1beta1NamespacedPodDisruptionBudgetStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_policy_v1beta1_namespaced_pod_disruption_budget_status"></a>![Method: ](https://apidocs.io/img/method.png ".PolicyV1beta1Controller.patchPolicyV1beta1NamespacedPodDisruptionBudgetStatus") patchPolicyV1beta1NamespacedPodDisruptionBudgetStatus

> partially update status of the specified PodDisruptionBudget


```php
function patchPolicyV1beta1NamespacedPodDisruptionBudgetStatus(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the PodDisruptionBudget |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $policyV1beta1->patchPolicyV1beta1NamespacedPodDisruptionBudgetStatus($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_policy_v1beta1_pod_disruption_budget_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".PolicyV1beta1Controller.listPolicyV1beta1PodDisruptionBudgetForAllNamespaces") listPolicyV1beta1PodDisruptionBudgetForAllNamespaces

> list or watch objects of kind PodDisruptionBudget


```php
function listPolicyV1beta1PodDisruptionBudgetForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 169;
$watch = true;

$result = $policyV1beta1->listPolicyV1beta1PodDisruptionBudgetForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_policy_v1beta1_namespaced_pod_disruption_budget_list"></a>![Method: ](https://apidocs.io/img/method.png ".PolicyV1beta1Controller.getWatchPolicyV1beta1NamespacedPodDisruptionBudgetList") getWatchPolicyV1beta1NamespacedPodDisruptionBudgetList

> watch individual changes to a list of PodDisruptionBudget


```php
function getWatchPolicyV1beta1NamespacedPodDisruptionBudgetList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 169;
$watch = true;

$result = $policyV1beta1->getWatchPolicyV1beta1NamespacedPodDisruptionBudgetList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_policy_v1beta1_namespaced_pod_disruption_budget"></a>![Method: ](https://apidocs.io/img/method.png ".PolicyV1beta1Controller.getWatchPolicyV1beta1NamespacedPodDisruptionBudget") getWatchPolicyV1beta1NamespacedPodDisruptionBudget

> watch changes to an object of kind PodDisruptionBudget


```php
function getWatchPolicyV1beta1NamespacedPodDisruptionBudget(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the PodDisruptionBudget |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 169;
$watch = true;

$result = $policyV1beta1->getWatchPolicyV1beta1NamespacedPodDisruptionBudget($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_policy_v1beta1_pod_disruption_budget_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".PolicyV1beta1Controller.getWatchPolicyV1beta1PodDisruptionBudgetListForAllNamespaces") getWatchPolicyV1beta1PodDisruptionBudgetListForAllNamespaces

> watch individual changes to a list of PodDisruptionBudget


```php
function getWatchPolicyV1beta1PodDisruptionBudgetListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 6;
$watch = false;

$result = $policyV1beta1->getWatchPolicyV1beta1PodDisruptionBudgetListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="rbac_authorization_controller"></a>![Class: ](https://apidocs.io/img/class.png ".RbacAuthorizationController") RbacAuthorizationController

### Get singleton instance

The singleton instance of the ``` RbacAuthorizationController ``` class can be accessed from the API Client.

```php
$rbacAuthorization = $client->getRbacAuthorization();
```

### <a name="get_rbac_authorization_api_group"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationController.getRbacAuthorizationAPIGroup") getRbacAuthorizationAPIGroup

> get information of a group


```php
function getRbacAuthorizationAPIGroup()
```

#### Example Usage

```php

$result = $rbacAuthorization->getRbacAuthorizationAPIGroup();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="rbac_authorization_v1alpha1_controller"></a>![Class: ](https://apidocs.io/img/class.png ".RbacAuthorizationV1alpha1Controller") RbacAuthorizationV1alpha1Controller

### Get singleton instance

The singleton instance of the ``` RbacAuthorizationV1alpha1Controller ``` class can be accessed from the API Client.

```php
$rbacAuthorizationV1alpha1 = $client->getRbacAuthorizationV1alpha1();
```

### <a name="get_rbac_authorization_v1alpha1_api_resources"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.getRbacAuthorizationV1alpha1APIResources") getRbacAuthorizationV1alpha1APIResources

> get available resources


```php
function getRbacAuthorizationV1alpha1APIResources()
```

#### Example Usage

```php

$result = $rbacAuthorizationV1alpha1->getRbacAuthorizationV1alpha1APIResources();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_rbac_authorization_v1alpha1_cluster_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.listRbacAuthorizationV1alpha1ClusterRoleBinding") listRbacAuthorizationV1alpha1ClusterRoleBinding

> list or watch objects of kind ClusterRoleBinding


```php
function listRbacAuthorizationV1alpha1ClusterRoleBinding(
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 6;
$watch = false;
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->listRbacAuthorizationV1alpha1ClusterRoleBinding($fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_rbac_authorization_v1alpha1_cluster_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.createRbacAuthorizationV1alpha1ClusterRoleBinding") createRbacAuthorizationV1alpha1ClusterRoleBinding

> create a ClusterRoleBinding


```php
function createRbacAuthorizationV1alpha1ClusterRoleBinding(
        $body,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisRbacV1alpha1ClusterRoleBinding();
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->createRbacAuthorizationV1alpha1ClusterRoleBinding($body, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_rbac_authorization_v1alpha1_collection_cluster_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.deleteRbacAuthorizationV1alpha1CollectionClusterRoleBinding") deleteRbacAuthorizationV1alpha1CollectionClusterRoleBinding

> delete collection of ClusterRoleBinding


```php
function deleteRbacAuthorizationV1alpha1CollectionClusterRoleBinding(
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 6;
$watch = false;
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->deleteRbacAuthorizationV1alpha1CollectionClusterRoleBinding($fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_rbac_authorization_v1alpha1_cluster_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.getReadRbacAuthorizationV1alpha1ClusterRoleBinding") getReadRbacAuthorizationV1alpha1ClusterRoleBinding

> read the specified ClusterRoleBinding


```php
function getReadRbacAuthorizationV1alpha1ClusterRoleBinding(
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ClusterRoleBinding |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->getReadRbacAuthorizationV1alpha1ClusterRoleBinding($name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_rbac_authorization_v1alpha1_cluster_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.updateReplaceRbacAuthorizationV1alpha1ClusterRoleBinding") updateReplaceRbacAuthorizationV1alpha1ClusterRoleBinding

> replace the specified ClusterRoleBinding


```php
function updateReplaceRbacAuthorizationV1alpha1ClusterRoleBinding(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ClusterRoleBinding |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisRbacV1alpha1ClusterRoleBinding();
$name = 'name';
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->updateReplaceRbacAuthorizationV1alpha1ClusterRoleBinding($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_rbac_authorization_v1alpha1_cluster_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.deleteRbacAuthorizationV1alpha1ClusterRoleBinding") deleteRbacAuthorizationV1alpha1ClusterRoleBinding

> delete a ClusterRoleBinding


```php
function deleteRbacAuthorizationV1alpha1ClusterRoleBinding(
        $body,
        $name,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ClusterRoleBinding |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$gracePeriodSeconds = 6;
$orphanDependents = false;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->deleteRbacAuthorizationV1alpha1ClusterRoleBinding($body, $name, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_rbac_authorization_v1alpha1_cluster_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.patchRbacAuthorizationV1alpha1ClusterRoleBinding") patchRbacAuthorizationV1alpha1ClusterRoleBinding

> partially update the specified ClusterRoleBinding


```php
function patchRbacAuthorizationV1alpha1ClusterRoleBinding(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ClusterRoleBinding |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->patchRbacAuthorizationV1alpha1ClusterRoleBinding($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_rbac_authorization_v1alpha1_cluster_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.listRbacAuthorizationV1alpha1ClusterRole") listRbacAuthorizationV1alpha1ClusterRole

> list or watch objects of kind ClusterRole


```php
function listRbacAuthorizationV1alpha1ClusterRole(
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 6;
$watch = false;
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->listRbacAuthorizationV1alpha1ClusterRole($fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_rbac_authorization_v1alpha1_cluster_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.createRbacAuthorizationV1alpha1ClusterRole") createRbacAuthorizationV1alpha1ClusterRole

> create a ClusterRole


```php
function createRbacAuthorizationV1alpha1ClusterRole(
        $body,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisRbacV1alpha1ClusterRole();
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->createRbacAuthorizationV1alpha1ClusterRole($body, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_rbac_authorization_v1alpha1_collection_cluster_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.deleteRbacAuthorizationV1alpha1CollectionClusterRole") deleteRbacAuthorizationV1alpha1CollectionClusterRole

> delete collection of ClusterRole


```php
function deleteRbacAuthorizationV1alpha1CollectionClusterRole(
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 6;
$watch = false;
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->deleteRbacAuthorizationV1alpha1CollectionClusterRole($fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_rbac_authorization_v1alpha1_cluster_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.getReadRbacAuthorizationV1alpha1ClusterRole") getReadRbacAuthorizationV1alpha1ClusterRole

> read the specified ClusterRole


```php
function getReadRbacAuthorizationV1alpha1ClusterRole(
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ClusterRole |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->getReadRbacAuthorizationV1alpha1ClusterRole($name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_rbac_authorization_v1alpha1_cluster_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.updateReplaceRbacAuthorizationV1alpha1ClusterRole") updateReplaceRbacAuthorizationV1alpha1ClusterRole

> replace the specified ClusterRole


```php
function updateReplaceRbacAuthorizationV1alpha1ClusterRole(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ClusterRole |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisRbacV1alpha1ClusterRole();
$name = 'name';
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->updateReplaceRbacAuthorizationV1alpha1ClusterRole($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_rbac_authorization_v1alpha1_cluster_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.deleteRbacAuthorizationV1alpha1ClusterRole") deleteRbacAuthorizationV1alpha1ClusterRole

> delete a ClusterRole


```php
function deleteRbacAuthorizationV1alpha1ClusterRole(
        $body,
        $name,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ClusterRole |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$gracePeriodSeconds = 6;
$orphanDependents = false;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->deleteRbacAuthorizationV1alpha1ClusterRole($body, $name, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_rbac_authorization_v1alpha1_cluster_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.patchRbacAuthorizationV1alpha1ClusterRole") patchRbacAuthorizationV1alpha1ClusterRole

> partially update the specified ClusterRole


```php
function patchRbacAuthorizationV1alpha1ClusterRole(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ClusterRole |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->patchRbacAuthorizationV1alpha1ClusterRole($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_rbac_authorization_v1alpha1_namespaced_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.listRbacAuthorizationV1alpha1NamespacedRoleBinding") listRbacAuthorizationV1alpha1NamespacedRoleBinding

> list or watch objects of kind RoleBinding


```php
function listRbacAuthorizationV1alpha1NamespacedRoleBinding(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 219;
$watch = true;
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->listRbacAuthorizationV1alpha1NamespacedRoleBinding($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_rbac_authorization_v1alpha1_namespaced_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.createRbacAuthorizationV1alpha1NamespacedRoleBinding") createRbacAuthorizationV1alpha1NamespacedRoleBinding

> create a RoleBinding


```php
function createRbacAuthorizationV1alpha1NamespacedRoleBinding(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisRbacV1alpha1ClusterRoleBinding();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->createRbacAuthorizationV1alpha1NamespacedRoleBinding($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_rbac_authorization_v1alpha1_collection_namespaced_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.deleteRbacAuthorizationV1alpha1CollectionNamespacedRoleBinding") deleteRbacAuthorizationV1alpha1CollectionNamespacedRoleBinding

> delete collection of RoleBinding


```php
function deleteRbacAuthorizationV1alpha1CollectionNamespacedRoleBinding(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 219;
$watch = true;
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->deleteRbacAuthorizationV1alpha1CollectionNamespacedRoleBinding($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_rbac_authorization_v1alpha1_namespaced_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.getReadRbacAuthorizationV1alpha1NamespacedRoleBinding") getReadRbacAuthorizationV1alpha1NamespacedRoleBinding

> read the specified RoleBinding


```php
function getReadRbacAuthorizationV1alpha1NamespacedRoleBinding(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the RoleBinding |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->getReadRbacAuthorizationV1alpha1NamespacedRoleBinding($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_rbac_authorization_v1alpha1_namespaced_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.updateReplaceRbacAuthorizationV1alpha1NamespacedRoleBinding") updateReplaceRbacAuthorizationV1alpha1NamespacedRoleBinding

> replace the specified RoleBinding


```php
function updateReplaceRbacAuthorizationV1alpha1NamespacedRoleBinding(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the RoleBinding |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisRbacV1alpha1ClusterRoleBinding();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->updateReplaceRbacAuthorizationV1alpha1NamespacedRoleBinding($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_rbac_authorization_v1alpha1_namespaced_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.deleteRbacAuthorizationV1alpha1NamespacedRoleBinding") deleteRbacAuthorizationV1alpha1NamespacedRoleBinding

> delete a RoleBinding


```php
function deleteRbacAuthorizationV1alpha1NamespacedRoleBinding(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the RoleBinding |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 219;
$orphanDependents = true;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->deleteRbacAuthorizationV1alpha1NamespacedRoleBinding($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_rbac_authorization_v1alpha1_namespaced_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.patchRbacAuthorizationV1alpha1NamespacedRoleBinding") patchRbacAuthorizationV1alpha1NamespacedRoleBinding

> partially update the specified RoleBinding


```php
function patchRbacAuthorizationV1alpha1NamespacedRoleBinding(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the RoleBinding |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->patchRbacAuthorizationV1alpha1NamespacedRoleBinding($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_rbac_authorization_v1alpha1_namespaced_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.listRbacAuthorizationV1alpha1NamespacedRole") listRbacAuthorizationV1alpha1NamespacedRole

> list or watch objects of kind Role


```php
function listRbacAuthorizationV1alpha1NamespacedRole(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 219;
$watch = true;
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->listRbacAuthorizationV1alpha1NamespacedRole($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_rbac_authorization_v1alpha1_namespaced_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.createRbacAuthorizationV1alpha1NamespacedRole") createRbacAuthorizationV1alpha1NamespacedRole

> create a Role


```php
function createRbacAuthorizationV1alpha1NamespacedRole(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisRbacV1alpha1ClusterRole();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->createRbacAuthorizationV1alpha1NamespacedRole($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_rbac_authorization_v1alpha1_collection_namespaced_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.deleteRbacAuthorizationV1alpha1CollectionNamespacedRole") deleteRbacAuthorizationV1alpha1CollectionNamespacedRole

> delete collection of Role


```php
function deleteRbacAuthorizationV1alpha1CollectionNamespacedRole(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 219;
$watch = true;
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->deleteRbacAuthorizationV1alpha1CollectionNamespacedRole($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_rbac_authorization_v1alpha1_namespaced_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.getReadRbacAuthorizationV1alpha1NamespacedRole") getReadRbacAuthorizationV1alpha1NamespacedRole

> read the specified Role


```php
function getReadRbacAuthorizationV1alpha1NamespacedRole(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Role |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->getReadRbacAuthorizationV1alpha1NamespacedRole($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_rbac_authorization_v1alpha1_namespaced_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.updateReplaceRbacAuthorizationV1alpha1NamespacedRole") updateReplaceRbacAuthorizationV1alpha1NamespacedRole

> replace the specified Role


```php
function updateReplaceRbacAuthorizationV1alpha1NamespacedRole(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Role |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisRbacV1alpha1ClusterRole();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->updateReplaceRbacAuthorizationV1alpha1NamespacedRole($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_rbac_authorization_v1alpha1_namespaced_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.deleteRbacAuthorizationV1alpha1NamespacedRole") deleteRbacAuthorizationV1alpha1NamespacedRole

> delete a Role


```php
function deleteRbacAuthorizationV1alpha1NamespacedRole(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Role |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 219;
$orphanDependents = true;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->deleteRbacAuthorizationV1alpha1NamespacedRole($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_rbac_authorization_v1alpha1_namespaced_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.patchRbacAuthorizationV1alpha1NamespacedRole") patchRbacAuthorizationV1alpha1NamespacedRole

> partially update the specified Role


```php
function patchRbacAuthorizationV1alpha1NamespacedRole(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Role |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $rbacAuthorizationV1alpha1->patchRbacAuthorizationV1alpha1NamespacedRole($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_rbac_authorization_v1alpha1_role_binding_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.listRbacAuthorizationV1alpha1RoleBindingForAllNamespaces") listRbacAuthorizationV1alpha1RoleBindingForAllNamespaces

> list or watch objects of kind RoleBinding


```php
function listRbacAuthorizationV1alpha1RoleBindingForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 56;
$watch = false;

$result = $rbacAuthorizationV1alpha1->listRbacAuthorizationV1alpha1RoleBindingForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_rbac_authorization_v1alpha1_role_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.listRbacAuthorizationV1alpha1RoleForAllNamespaces") listRbacAuthorizationV1alpha1RoleForAllNamespaces

> list or watch objects of kind Role


```php
function listRbacAuthorizationV1alpha1RoleForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 56;
$watch = false;

$result = $rbacAuthorizationV1alpha1->listRbacAuthorizationV1alpha1RoleForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_rbac_authorization_v1alpha1_cluster_role_binding_list"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.getWatchRbacAuthorizationV1alpha1ClusterRoleBindingList") getWatchRbacAuthorizationV1alpha1ClusterRoleBindingList

> watch individual changes to a list of ClusterRoleBinding


```php
function getWatchRbacAuthorizationV1alpha1ClusterRoleBindingList(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 56;
$watch = false;

$result = $rbacAuthorizationV1alpha1->getWatchRbacAuthorizationV1alpha1ClusterRoleBindingList($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_rbac_authorization_v1alpha1_cluster_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.getWatchRbacAuthorizationV1alpha1ClusterRoleBinding") getWatchRbacAuthorizationV1alpha1ClusterRoleBinding

> watch changes to an object of kind ClusterRoleBinding


```php
function getWatchRbacAuthorizationV1alpha1ClusterRoleBinding(
        $name,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ClusterRoleBinding |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 56;
$watch = false;

$result = $rbacAuthorizationV1alpha1->getWatchRbacAuthorizationV1alpha1ClusterRoleBinding($name, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_rbac_authorization_v1alpha1_cluster_role_list"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.getWatchRbacAuthorizationV1alpha1ClusterRoleList") getWatchRbacAuthorizationV1alpha1ClusterRoleList

> watch individual changes to a list of ClusterRole


```php
function getWatchRbacAuthorizationV1alpha1ClusterRoleList(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 56;
$watch = false;

$result = $rbacAuthorizationV1alpha1->getWatchRbacAuthorizationV1alpha1ClusterRoleList($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_rbac_authorization_v1alpha1_cluster_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.getWatchRbacAuthorizationV1alpha1ClusterRole") getWatchRbacAuthorizationV1alpha1ClusterRole

> watch changes to an object of kind ClusterRole


```php
function getWatchRbacAuthorizationV1alpha1ClusterRole(
        $name,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ClusterRole |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 56;
$watch = false;

$result = $rbacAuthorizationV1alpha1->getWatchRbacAuthorizationV1alpha1ClusterRole($name, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_rbac_authorization_v1alpha1_namespaced_role_binding_list"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.getWatchRbacAuthorizationV1alpha1NamespacedRoleBindingList") getWatchRbacAuthorizationV1alpha1NamespacedRoleBindingList

> watch individual changes to a list of RoleBinding


```php
function getWatchRbacAuthorizationV1alpha1NamespacedRoleBindingList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 56;
$watch = false;

$result = $rbacAuthorizationV1alpha1->getWatchRbacAuthorizationV1alpha1NamespacedRoleBindingList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_rbac_authorization_v1alpha1_namespaced_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.getWatchRbacAuthorizationV1alpha1NamespacedRoleBinding") getWatchRbacAuthorizationV1alpha1NamespacedRoleBinding

> watch changes to an object of kind RoleBinding


```php
function getWatchRbacAuthorizationV1alpha1NamespacedRoleBinding(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the RoleBinding |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 56;
$watch = false;

$result = $rbacAuthorizationV1alpha1->getWatchRbacAuthorizationV1alpha1NamespacedRoleBinding($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_rbac_authorization_v1alpha1_namespaced_role_list"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.getWatchRbacAuthorizationV1alpha1NamespacedRoleList") getWatchRbacAuthorizationV1alpha1NamespacedRoleList

> watch individual changes to a list of Role


```php
function getWatchRbacAuthorizationV1alpha1NamespacedRoleList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 56;
$watch = false;

$result = $rbacAuthorizationV1alpha1->getWatchRbacAuthorizationV1alpha1NamespacedRoleList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_rbac_authorization_v1alpha1_namespaced_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.getWatchRbacAuthorizationV1alpha1NamespacedRole") getWatchRbacAuthorizationV1alpha1NamespacedRole

> watch changes to an object of kind Role


```php
function getWatchRbacAuthorizationV1alpha1NamespacedRole(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Role |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 56;
$watch = false;

$result = $rbacAuthorizationV1alpha1->getWatchRbacAuthorizationV1alpha1NamespacedRole($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_rbac_authorization_v1alpha1_role_binding_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.getWatchRbacAuthorizationV1alpha1RoleBindingListForAllNamespaces") getWatchRbacAuthorizationV1alpha1RoleBindingListForAllNamespaces

> watch individual changes to a list of RoleBinding


```php
function getWatchRbacAuthorizationV1alpha1RoleBindingListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 147;
$watch = true;

$result = $rbacAuthorizationV1alpha1->getWatchRbacAuthorizationV1alpha1RoleBindingListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_rbac_authorization_v1alpha1_role_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1alpha1Controller.getWatchRbacAuthorizationV1alpha1RoleListForAllNamespaces") getWatchRbacAuthorizationV1alpha1RoleListForAllNamespaces

> watch individual changes to a list of Role


```php
function getWatchRbacAuthorizationV1alpha1RoleListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 147;
$watch = true;

$result = $rbacAuthorizationV1alpha1->getWatchRbacAuthorizationV1alpha1RoleListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="rbac_authorization_v1beta1_controller"></a>![Class: ](https://apidocs.io/img/class.png ".RbacAuthorizationV1beta1Controller") RbacAuthorizationV1beta1Controller

### Get singleton instance

The singleton instance of the ``` RbacAuthorizationV1beta1Controller ``` class can be accessed from the API Client.

```php
$rbacAuthorizationV1beta1 = $client->getRbacAuthorizationV1beta1();
```

### <a name="get_rbac_authorization_v1beta1_api_resources"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.getRbacAuthorizationV1beta1APIResources") getRbacAuthorizationV1beta1APIResources

> get available resources


```php
function getRbacAuthorizationV1beta1APIResources()
```

#### Example Usage

```php

$result = $rbacAuthorizationV1beta1->getRbacAuthorizationV1beta1APIResources();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_rbac_authorization_v1beta1_cluster_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.listRbacAuthorizationV1beta1ClusterRoleBinding") listRbacAuthorizationV1beta1ClusterRoleBinding

> list or watch objects of kind ClusterRoleBinding


```php
function listRbacAuthorizationV1beta1ClusterRoleBinding(
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 147;
$watch = true;
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->listRbacAuthorizationV1beta1ClusterRoleBinding($fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_rbac_authorization_v1beta1_cluster_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.createRbacAuthorizationV1beta1ClusterRoleBinding") createRbacAuthorizationV1beta1ClusterRoleBinding

> create a ClusterRoleBinding


```php
function createRbacAuthorizationV1beta1ClusterRoleBinding(
        $body,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisRbacV1beta1ClusterRoleBinding();
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->createRbacAuthorizationV1beta1ClusterRoleBinding($body, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_rbac_authorization_v1beta1_collection_cluster_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.deleteRbacAuthorizationV1beta1CollectionClusterRoleBinding") deleteRbacAuthorizationV1beta1CollectionClusterRoleBinding

> delete collection of ClusterRoleBinding


```php
function deleteRbacAuthorizationV1beta1CollectionClusterRoleBinding(
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 147;
$watch = true;
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->deleteRbacAuthorizationV1beta1CollectionClusterRoleBinding($fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_rbac_authorization_v1beta1_cluster_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.getReadRbacAuthorizationV1beta1ClusterRoleBinding") getReadRbacAuthorizationV1beta1ClusterRoleBinding

> read the specified ClusterRoleBinding


```php
function getReadRbacAuthorizationV1beta1ClusterRoleBinding(
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ClusterRoleBinding |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->getReadRbacAuthorizationV1beta1ClusterRoleBinding($name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_rbac_authorization_v1beta1_cluster_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.updateReplaceRbacAuthorizationV1beta1ClusterRoleBinding") updateReplaceRbacAuthorizationV1beta1ClusterRoleBinding

> replace the specified ClusterRoleBinding


```php
function updateReplaceRbacAuthorizationV1beta1ClusterRoleBinding(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ClusterRoleBinding |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisRbacV1beta1ClusterRoleBinding();
$name = 'name';
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->updateReplaceRbacAuthorizationV1beta1ClusterRoleBinding($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_rbac_authorization_v1beta1_cluster_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.deleteRbacAuthorizationV1beta1ClusterRoleBinding") deleteRbacAuthorizationV1beta1ClusterRoleBinding

> delete a ClusterRoleBinding


```php
function deleteRbacAuthorizationV1beta1ClusterRoleBinding(
        $body,
        $name,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ClusterRoleBinding |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$gracePeriodSeconds = 147;
$orphanDependents = true;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->deleteRbacAuthorizationV1beta1ClusterRoleBinding($body, $name, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_rbac_authorization_v1beta1_cluster_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.patchRbacAuthorizationV1beta1ClusterRoleBinding") patchRbacAuthorizationV1beta1ClusterRoleBinding

> partially update the specified ClusterRoleBinding


```php
function patchRbacAuthorizationV1beta1ClusterRoleBinding(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ClusterRoleBinding |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->patchRbacAuthorizationV1beta1ClusterRoleBinding($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_rbac_authorization_v1beta1_cluster_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.listRbacAuthorizationV1beta1ClusterRole") listRbacAuthorizationV1beta1ClusterRole

> list or watch objects of kind ClusterRole


```php
function listRbacAuthorizationV1beta1ClusterRole(
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 147;
$watch = true;
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->listRbacAuthorizationV1beta1ClusterRole($fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_rbac_authorization_v1beta1_cluster_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.createRbacAuthorizationV1beta1ClusterRole") createRbacAuthorizationV1beta1ClusterRole

> create a ClusterRole


```php
function createRbacAuthorizationV1beta1ClusterRole(
        $body,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisRbacV1alpha1ClusterRole();
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->createRbacAuthorizationV1beta1ClusterRole($body, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_rbac_authorization_v1beta1_collection_cluster_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.deleteRbacAuthorizationV1beta1CollectionClusterRole") deleteRbacAuthorizationV1beta1CollectionClusterRole

> delete collection of ClusterRole


```php
function deleteRbacAuthorizationV1beta1CollectionClusterRole(
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 147;
$watch = true;
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->deleteRbacAuthorizationV1beta1CollectionClusterRole($fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_rbac_authorization_v1beta1_cluster_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.getReadRbacAuthorizationV1beta1ClusterRole") getReadRbacAuthorizationV1beta1ClusterRole

> read the specified ClusterRole


```php
function getReadRbacAuthorizationV1beta1ClusterRole(
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ClusterRole |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->getReadRbacAuthorizationV1beta1ClusterRole($name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_rbac_authorization_v1beta1_cluster_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.updateReplaceRbacAuthorizationV1beta1ClusterRole") updateReplaceRbacAuthorizationV1beta1ClusterRole

> replace the specified ClusterRole


```php
function updateReplaceRbacAuthorizationV1beta1ClusterRole(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ClusterRole |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisRbacV1alpha1ClusterRole();
$name = 'name';
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->updateReplaceRbacAuthorizationV1beta1ClusterRole($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_rbac_authorization_v1beta1_cluster_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.deleteRbacAuthorizationV1beta1ClusterRole") deleteRbacAuthorizationV1beta1ClusterRole

> delete a ClusterRole


```php
function deleteRbacAuthorizationV1beta1ClusterRole(
        $body,
        $name,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ClusterRole |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$gracePeriodSeconds = 147;
$orphanDependents = true;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->deleteRbacAuthorizationV1beta1ClusterRole($body, $name, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_rbac_authorization_v1beta1_cluster_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.patchRbacAuthorizationV1beta1ClusterRole") patchRbacAuthorizationV1beta1ClusterRole

> partially update the specified ClusterRole


```php
function patchRbacAuthorizationV1beta1ClusterRole(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the ClusterRole |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->patchRbacAuthorizationV1beta1ClusterRole($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_rbac_authorization_v1beta1_namespaced_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.listRbacAuthorizationV1beta1NamespacedRoleBinding") listRbacAuthorizationV1beta1NamespacedRoleBinding

> list or watch objects of kind RoleBinding


```php
function listRbacAuthorizationV1beta1NamespacedRoleBinding(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 105;
$watch = false;
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->listRbacAuthorizationV1beta1NamespacedRoleBinding($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_rbac_authorization_v1beta1_namespaced_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.createRbacAuthorizationV1beta1NamespacedRoleBinding") createRbacAuthorizationV1beta1NamespacedRoleBinding

> create a RoleBinding


```php
function createRbacAuthorizationV1beta1NamespacedRoleBinding(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisRbacV1beta1ClusterRoleBinding();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->createRbacAuthorizationV1beta1NamespacedRoleBinding($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_rbac_authorization_v1beta1_collection_namespaced_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.deleteRbacAuthorizationV1beta1CollectionNamespacedRoleBinding") deleteRbacAuthorizationV1beta1CollectionNamespacedRoleBinding

> delete collection of RoleBinding


```php
function deleteRbacAuthorizationV1beta1CollectionNamespacedRoleBinding(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 105;
$watch = false;
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->deleteRbacAuthorizationV1beta1CollectionNamespacedRoleBinding($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_rbac_authorization_v1beta1_namespaced_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.getReadRbacAuthorizationV1beta1NamespacedRoleBinding") getReadRbacAuthorizationV1beta1NamespacedRoleBinding

> read the specified RoleBinding


```php
function getReadRbacAuthorizationV1beta1NamespacedRoleBinding(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the RoleBinding |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->getReadRbacAuthorizationV1beta1NamespacedRoleBinding($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_rbac_authorization_v1beta1_namespaced_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.updateReplaceRbacAuthorizationV1beta1NamespacedRoleBinding") updateReplaceRbacAuthorizationV1beta1NamespacedRoleBinding

> replace the specified RoleBinding


```php
function updateReplaceRbacAuthorizationV1beta1NamespacedRoleBinding(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the RoleBinding |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisRbacV1beta1ClusterRoleBinding();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->updateReplaceRbacAuthorizationV1beta1NamespacedRoleBinding($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_rbac_authorization_v1beta1_namespaced_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.deleteRbacAuthorizationV1beta1NamespacedRoleBinding") deleteRbacAuthorizationV1beta1NamespacedRoleBinding

> delete a RoleBinding


```php
function deleteRbacAuthorizationV1beta1NamespacedRoleBinding(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the RoleBinding |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 105;
$orphanDependents = false;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->deleteRbacAuthorizationV1beta1NamespacedRoleBinding($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_rbac_authorization_v1beta1_namespaced_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.patchRbacAuthorizationV1beta1NamespacedRoleBinding") patchRbacAuthorizationV1beta1NamespacedRoleBinding

> partially update the specified RoleBinding


```php
function patchRbacAuthorizationV1beta1NamespacedRoleBinding(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the RoleBinding |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->patchRbacAuthorizationV1beta1NamespacedRoleBinding($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_rbac_authorization_v1beta1_namespaced_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.listRbacAuthorizationV1beta1NamespacedRole") listRbacAuthorizationV1beta1NamespacedRole

> list or watch objects of kind Role


```php
function listRbacAuthorizationV1beta1NamespacedRole(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 105;
$watch = false;
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->listRbacAuthorizationV1beta1NamespacedRole($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_rbac_authorization_v1beta1_namespaced_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.createRbacAuthorizationV1beta1NamespacedRole") createRbacAuthorizationV1beta1NamespacedRole

> create a Role


```php
function createRbacAuthorizationV1beta1NamespacedRole(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisRbacV1alpha1ClusterRole();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->createRbacAuthorizationV1beta1NamespacedRole($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_rbac_authorization_v1beta1_collection_namespaced_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.deleteRbacAuthorizationV1beta1CollectionNamespacedRole") deleteRbacAuthorizationV1beta1CollectionNamespacedRole

> delete collection of Role


```php
function deleteRbacAuthorizationV1beta1CollectionNamespacedRole(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 105;
$watch = false;
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->deleteRbacAuthorizationV1beta1CollectionNamespacedRole($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_rbac_authorization_v1beta1_namespaced_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.getReadRbacAuthorizationV1beta1NamespacedRole") getReadRbacAuthorizationV1beta1NamespacedRole

> read the specified Role


```php
function getReadRbacAuthorizationV1beta1NamespacedRole(
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Role |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->getReadRbacAuthorizationV1beta1NamespacedRole($name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_rbac_authorization_v1beta1_namespaced_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.updateReplaceRbacAuthorizationV1beta1NamespacedRole") updateReplaceRbacAuthorizationV1beta1NamespacedRole

> replace the specified Role


```php
function updateReplaceRbacAuthorizationV1beta1NamespacedRole(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Role |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisRbacV1alpha1ClusterRole();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->updateReplaceRbacAuthorizationV1beta1NamespacedRole($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_rbac_authorization_v1beta1_namespaced_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.deleteRbacAuthorizationV1beta1NamespacedRole") deleteRbacAuthorizationV1beta1NamespacedRole

> delete a Role


```php
function deleteRbacAuthorizationV1beta1NamespacedRole(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Role |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 105;
$orphanDependents = false;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->deleteRbacAuthorizationV1beta1NamespacedRole($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_rbac_authorization_v1beta1_namespaced_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.patchRbacAuthorizationV1beta1NamespacedRole") patchRbacAuthorizationV1beta1NamespacedRole

> partially update the specified Role


```php
function patchRbacAuthorizationV1beta1NamespacedRole(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the Role |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $rbacAuthorizationV1beta1->patchRbacAuthorizationV1beta1NamespacedRole($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_rbac_authorization_v1beta1_role_binding_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.listRbacAuthorizationV1beta1RoleBindingForAllNamespaces") listRbacAuthorizationV1beta1RoleBindingForAllNamespaces

> list or watch objects of kind RoleBinding


```php
function listRbacAuthorizationV1beta1RoleBindingForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 197;
$watch = true;

$result = $rbacAuthorizationV1beta1->listRbacAuthorizationV1beta1RoleBindingForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_rbac_authorization_v1beta1_role_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.listRbacAuthorizationV1beta1RoleForAllNamespaces") listRbacAuthorizationV1beta1RoleForAllNamespaces

> list or watch objects of kind Role


```php
function listRbacAuthorizationV1beta1RoleForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 197;
$watch = true;

$result = $rbacAuthorizationV1beta1->listRbacAuthorizationV1beta1RoleForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_rbac_authorization_v1beta1_cluster_role_binding_list"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.getWatchRbacAuthorizationV1beta1ClusterRoleBindingList") getWatchRbacAuthorizationV1beta1ClusterRoleBindingList

> watch individual changes to a list of ClusterRoleBinding


```php
function getWatchRbacAuthorizationV1beta1ClusterRoleBindingList(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 197;
$watch = true;

$result = $rbacAuthorizationV1beta1->getWatchRbacAuthorizationV1beta1ClusterRoleBindingList($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_rbac_authorization_v1beta1_cluster_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.getWatchRbacAuthorizationV1beta1ClusterRoleBinding") getWatchRbacAuthorizationV1beta1ClusterRoleBinding

> watch changes to an object of kind ClusterRoleBinding


```php
function getWatchRbacAuthorizationV1beta1ClusterRoleBinding(
        $name,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ClusterRoleBinding |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 197;
$watch = true;

$result = $rbacAuthorizationV1beta1->getWatchRbacAuthorizationV1beta1ClusterRoleBinding($name, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_rbac_authorization_v1beta1_cluster_role_list"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.getWatchRbacAuthorizationV1beta1ClusterRoleList") getWatchRbacAuthorizationV1beta1ClusterRoleList

> watch individual changes to a list of ClusterRole


```php
function getWatchRbacAuthorizationV1beta1ClusterRoleList(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 197;
$watch = true;

$result = $rbacAuthorizationV1beta1->getWatchRbacAuthorizationV1beta1ClusterRoleList($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_rbac_authorization_v1beta1_cluster_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.getWatchRbacAuthorizationV1beta1ClusterRole") getWatchRbacAuthorizationV1beta1ClusterRole

> watch changes to an object of kind ClusterRole


```php
function getWatchRbacAuthorizationV1beta1ClusterRole(
        $name,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the ClusterRole |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 197;
$watch = true;

$result = $rbacAuthorizationV1beta1->getWatchRbacAuthorizationV1beta1ClusterRole($name, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_rbac_authorization_v1beta1_namespaced_role_binding_list"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.getWatchRbacAuthorizationV1beta1NamespacedRoleBindingList") getWatchRbacAuthorizationV1beta1NamespacedRoleBindingList

> watch individual changes to a list of RoleBinding


```php
function getWatchRbacAuthorizationV1beta1NamespacedRoleBindingList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 197;
$watch = true;

$result = $rbacAuthorizationV1beta1->getWatchRbacAuthorizationV1beta1NamespacedRoleBindingList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_rbac_authorization_v1beta1_namespaced_role_binding"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.getWatchRbacAuthorizationV1beta1NamespacedRoleBinding") getWatchRbacAuthorizationV1beta1NamespacedRoleBinding

> watch changes to an object of kind RoleBinding


```php
function getWatchRbacAuthorizationV1beta1NamespacedRoleBinding(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the RoleBinding |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 197;
$watch = true;

$result = $rbacAuthorizationV1beta1->getWatchRbacAuthorizationV1beta1NamespacedRoleBinding($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_rbac_authorization_v1beta1_namespaced_role_list"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.getWatchRbacAuthorizationV1beta1NamespacedRoleList") getWatchRbacAuthorizationV1beta1NamespacedRoleList

> watch individual changes to a list of Role


```php
function getWatchRbacAuthorizationV1beta1NamespacedRoleList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 197;
$watch = true;

$result = $rbacAuthorizationV1beta1->getWatchRbacAuthorizationV1beta1NamespacedRoleList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_rbac_authorization_v1beta1_namespaced_role"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.getWatchRbacAuthorizationV1beta1NamespacedRole") getWatchRbacAuthorizationV1beta1NamespacedRole

> watch changes to an object of kind Role


```php
function getWatchRbacAuthorizationV1beta1NamespacedRole(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the Role |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 197;
$watch = true;

$result = $rbacAuthorizationV1beta1->getWatchRbacAuthorizationV1beta1NamespacedRole($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_rbac_authorization_v1beta1_role_binding_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.getWatchRbacAuthorizationV1beta1RoleBindingListForAllNamespaces") getWatchRbacAuthorizationV1beta1RoleBindingListForAllNamespaces

> watch individual changes to a list of RoleBinding


```php
function getWatchRbacAuthorizationV1beta1RoleBindingListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 197;
$watch = true;

$result = $rbacAuthorizationV1beta1->getWatchRbacAuthorizationV1beta1RoleBindingListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_rbac_authorization_v1beta1_role_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".RbacAuthorizationV1beta1Controller.getWatchRbacAuthorizationV1beta1RoleListForAllNamespaces") getWatchRbacAuthorizationV1beta1RoleListForAllNamespaces

> watch individual changes to a list of Role


```php
function getWatchRbacAuthorizationV1beta1RoleListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 155;
$watch = true;

$result = $rbacAuthorizationV1beta1->getWatchRbacAuthorizationV1beta1RoleListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="settings_controller"></a>![Class: ](https://apidocs.io/img/class.png ".SettingsController") SettingsController

### Get singleton instance

The singleton instance of the ``` SettingsController ``` class can be accessed from the API Client.

```php
$settings = $client->getSettings();
```

### <a name="get_settings_api_group"></a>![Method: ](https://apidocs.io/img/method.png ".SettingsController.getSettingsAPIGroup") getSettingsAPIGroup

> get information of a group


```php
function getSettingsAPIGroup()
```

#### Example Usage

```php

$result = $settings->getSettingsAPIGroup();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="settings_v1alpha1_controller"></a>![Class: ](https://apidocs.io/img/class.png ".SettingsV1alpha1Controller") SettingsV1alpha1Controller

### Get singleton instance

The singleton instance of the ``` SettingsV1alpha1Controller ``` class can be accessed from the API Client.

```php
$settingsV1alpha1 = $client->getSettingsV1alpha1();
```

### <a name="get_settings_v1alpha1_api_resources"></a>![Method: ](https://apidocs.io/img/method.png ".SettingsV1alpha1Controller.getSettingsV1alpha1APIResources") getSettingsV1alpha1APIResources

> get available resources


```php
function getSettingsV1alpha1APIResources()
```

#### Example Usage

```php

$result = $settingsV1alpha1->getSettingsV1alpha1APIResources();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_settings_v1alpha1_namespaced_pod_preset"></a>![Method: ](https://apidocs.io/img/method.png ".SettingsV1alpha1Controller.listSettingsV1alpha1NamespacedPodPreset") listSettingsV1alpha1NamespacedPodPreset

> list or watch objects of kind PodPreset


```php
function listSettingsV1alpha1NamespacedPodPreset(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 155;
$watch = true;
$pretty = 'pretty';

$result = $settingsV1alpha1->listSettingsV1alpha1NamespacedPodPreset($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_settings_v1alpha1_namespaced_pod_preset"></a>![Method: ](https://apidocs.io/img/method.png ".SettingsV1alpha1Controller.createSettingsV1alpha1NamespacedPodPreset") createSettingsV1alpha1NamespacedPodPreset

> create a PodPreset


```php
function createSettingsV1alpha1NamespacedPodPreset(
        $body,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisSettingsV1alpha1PodPreset();
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $settingsV1alpha1->createSettingsV1alpha1NamespacedPodPreset($body, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_settings_v1alpha1_collection_namespaced_pod_preset"></a>![Method: ](https://apidocs.io/img/method.png ".SettingsV1alpha1Controller.deleteSettingsV1alpha1CollectionNamespacedPodPreset") deleteSettingsV1alpha1CollectionNamespacedPodPreset

> delete collection of PodPreset


```php
function deleteSettingsV1alpha1CollectionNamespacedPodPreset(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 155;
$watch = true;
$pretty = 'pretty';

$result = $settingsV1alpha1->deleteSettingsV1alpha1CollectionNamespacedPodPreset($mnamespace, $fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_settings_v1alpha1_namespaced_pod_preset"></a>![Method: ](https://apidocs.io/img/method.png ".SettingsV1alpha1Controller.getReadSettingsV1alpha1NamespacedPodPreset") getReadSettingsV1alpha1NamespacedPodPreset

> read the specified PodPreset


```php
function getReadSettingsV1alpha1NamespacedPodPreset(
        $name,
        $mnamespace,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the PodPreset |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$exact = true;
$export = true;
$pretty = 'pretty';

$result = $settingsV1alpha1->getReadSettingsV1alpha1NamespacedPodPreset($name, $mnamespace, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_settings_v1alpha1_namespaced_pod_preset"></a>![Method: ](https://apidocs.io/img/method.png ".SettingsV1alpha1Controller.updateReplaceSettingsV1alpha1NamespacedPodPreset") updateReplaceSettingsV1alpha1NamespacedPodPreset

> replace the specified PodPreset


```php
function updateReplaceSettingsV1alpha1NamespacedPodPreset(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the PodPreset |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisSettingsV1alpha1PodPreset();
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $settingsV1alpha1->updateReplaceSettingsV1alpha1NamespacedPodPreset($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_settings_v1alpha1_namespaced_pod_preset"></a>![Method: ](https://apidocs.io/img/method.png ".SettingsV1alpha1Controller.deleteSettingsV1alpha1NamespacedPodPreset") deleteSettingsV1alpha1NamespacedPodPreset

> delete a PodPreset


```php
function deleteSettingsV1alpha1NamespacedPodPreset(
        $body,
        $name,
        $mnamespace,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the PodPreset |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$mnamespace = 'namespace';
$gracePeriodSeconds = 155;
$orphanDependents = true;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $settingsV1alpha1->deleteSettingsV1alpha1NamespacedPodPreset($body, $name, $mnamespace, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_settings_v1alpha1_namespaced_pod_preset"></a>![Method: ](https://apidocs.io/img/method.png ".SettingsV1alpha1Controller.patchSettingsV1alpha1NamespacedPodPreset") patchSettingsV1alpha1NamespacedPodPreset

> partially update the specified PodPreset


```php
function patchSettingsV1alpha1NamespacedPodPreset(
        $body,
        $name,
        $mnamespace,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the PodPreset |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$mnamespace = 'namespace';
$pretty = 'pretty';

$result = $settingsV1alpha1->patchSettingsV1alpha1NamespacedPodPreset($body, $name, $mnamespace, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_settings_v1alpha1_pod_preset_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".SettingsV1alpha1Controller.listSettingsV1alpha1PodPresetForAllNamespaces") listSettingsV1alpha1PodPresetForAllNamespaces

> list or watch objects of kind PodPreset


```php
function listSettingsV1alpha1PodPresetForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 155;
$watch = true;

$result = $settingsV1alpha1->listSettingsV1alpha1PodPresetForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_settings_v1alpha1_namespaced_pod_preset_list"></a>![Method: ](https://apidocs.io/img/method.png ".SettingsV1alpha1Controller.getWatchSettingsV1alpha1NamespacedPodPresetList") getWatchSettingsV1alpha1NamespacedPodPresetList

> watch individual changes to a list of PodPreset


```php
function getWatchSettingsV1alpha1NamespacedPodPresetList(
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 155;
$watch = true;

$result = $settingsV1alpha1->getWatchSettingsV1alpha1NamespacedPodPresetList($mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_settings_v1alpha1_namespaced_pod_preset"></a>![Method: ](https://apidocs.io/img/method.png ".SettingsV1alpha1Controller.getWatchSettingsV1alpha1NamespacedPodPreset") getWatchSettingsV1alpha1NamespacedPodPreset

> watch changes to an object of kind PodPreset


```php
function getWatchSettingsV1alpha1NamespacedPodPreset(
        $name,
        $mnamespace,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the PodPreset |
| mnamespace |  ``` Required ```  | object name and auth scope, such as for teams and projects |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$mnamespace = 'namespace';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 155;
$watch = true;

$result = $settingsV1alpha1->getWatchSettingsV1alpha1NamespacedPodPreset($name, $mnamespace, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_settings_v1alpha1_pod_preset_list_for_all_namespaces"></a>![Method: ](https://apidocs.io/img/method.png ".SettingsV1alpha1Controller.getWatchSettingsV1alpha1PodPresetListForAllNamespaces") getWatchSettingsV1alpha1PodPresetListForAllNamespaces

> watch individual changes to a list of PodPreset


```php
function getWatchSettingsV1alpha1PodPresetListForAllNamespaces(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 247;
$watch = true;

$result = $settingsV1alpha1->getWatchSettingsV1alpha1PodPresetListForAllNamespaces($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="storage_controller"></a>![Class: ](https://apidocs.io/img/class.png ".StorageController") StorageController

### Get singleton instance

The singleton instance of the ``` StorageController ``` class can be accessed from the API Client.

```php
$storage = $client->getStorage();
```

### <a name="get_storage_api_group"></a>![Method: ](https://apidocs.io/img/method.png ".StorageController.getStorageAPIGroup") getStorageAPIGroup

> get information of a group


```php
function getStorageAPIGroup()
```

#### Example Usage

```php

$result = $storage->getStorageAPIGroup();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="storage_v1_controller"></a>![Class: ](https://apidocs.io/img/class.png ".StorageV1Controller") StorageV1Controller

### Get singleton instance

The singleton instance of the ``` StorageV1Controller ``` class can be accessed from the API Client.

```php
$storageV1 = $client->getStorageV1();
```

### <a name="get_storage_v1_api_resources"></a>![Method: ](https://apidocs.io/img/method.png ".StorageV1Controller.getStorageV1APIResources") getStorageV1APIResources

> get available resources


```php
function getStorageV1APIResources()
```

#### Example Usage

```php

$result = $storageV1->getStorageV1APIResources();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_storage_v1_storage_class"></a>![Method: ](https://apidocs.io/img/method.png ".StorageV1Controller.listStorageV1StorageClass") listStorageV1StorageClass

> list or watch objects of kind StorageClass


```php
function listStorageV1StorageClass(
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 247;
$watch = true;
$pretty = 'pretty';

$result = $storageV1->listStorageV1StorageClass($fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_storage_v1_storage_class"></a>![Method: ](https://apidocs.io/img/method.png ".StorageV1Controller.createStorageV1StorageClass") createStorageV1StorageClass

> create a StorageClass


```php
function createStorageV1StorageClass(
        $body,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisStorageV1StorageClass();
$pretty = 'pretty';

$result = $storageV1->createStorageV1StorageClass($body, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_storage_v1_collection_storage_class"></a>![Method: ](https://apidocs.io/img/method.png ".StorageV1Controller.deleteStorageV1CollectionStorageClass") deleteStorageV1CollectionStorageClass

> delete collection of StorageClass


```php
function deleteStorageV1CollectionStorageClass(
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 247;
$watch = true;
$pretty = 'pretty';

$result = $storageV1->deleteStorageV1CollectionStorageClass($fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_storage_v1_storage_class"></a>![Method: ](https://apidocs.io/img/method.png ".StorageV1Controller.getReadStorageV1StorageClass") getReadStorageV1StorageClass

> read the specified StorageClass


```php
function getReadStorageV1StorageClass(
        $name,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the StorageClass |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$exact = true;
$export = true;
$pretty = 'pretty';

$result = $storageV1->getReadStorageV1StorageClass($name, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_storage_v1_storage_class"></a>![Method: ](https://apidocs.io/img/method.png ".StorageV1Controller.updateReplaceStorageV1StorageClass") updateReplaceStorageV1StorageClass

> replace the specified StorageClass


```php
function updateReplaceStorageV1StorageClass(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the StorageClass |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisStorageV1StorageClass();
$name = 'name';
$pretty = 'pretty';

$result = $storageV1->updateReplaceStorageV1StorageClass($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_storage_v1_storage_class"></a>![Method: ](https://apidocs.io/img/method.png ".StorageV1Controller.deleteStorageV1StorageClass") deleteStorageV1StorageClass

> delete a StorageClass


```php
function deleteStorageV1StorageClass(
        $body,
        $name,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the StorageClass |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$gracePeriodSeconds = 83;
$orphanDependents = false;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $storageV1->deleteStorageV1StorageClass($body, $name, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_storage_v1_storage_class"></a>![Method: ](https://apidocs.io/img/method.png ".StorageV1Controller.patchStorageV1StorageClass") patchStorageV1StorageClass

> partially update the specified StorageClass


```php
function patchStorageV1StorageClass(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the StorageClass |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$pretty = 'pretty';

$result = $storageV1->patchStorageV1StorageClass($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_storage_v1_storage_class_list"></a>![Method: ](https://apidocs.io/img/method.png ".StorageV1Controller.getWatchStorageV1StorageClassList") getWatchStorageV1StorageClassList

> watch individual changes to a list of StorageClass


```php
function getWatchStorageV1StorageClassList(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 83;
$watch = false;

$result = $storageV1->getWatchStorageV1StorageClassList($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_storage_v1_storage_class"></a>![Method: ](https://apidocs.io/img/method.png ".StorageV1Controller.getWatchStorageV1StorageClass") getWatchStorageV1StorageClass

> watch changes to an object of kind StorageClass


```php
function getWatchStorageV1StorageClass(
        $name,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the StorageClass |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 83;
$watch = false;

$result = $storageV1->getWatchStorageV1StorageClass($name, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="storage_v1beta1_controller"></a>![Class: ](https://apidocs.io/img/class.png ".StorageV1beta1Controller") StorageV1beta1Controller

### Get singleton instance

The singleton instance of the ``` StorageV1beta1Controller ``` class can be accessed from the API Client.

```php
$storageV1beta1 = $client->getStorageV1beta1();
```

### <a name="get_storage_v1beta1_api_resources"></a>![Method: ](https://apidocs.io/img/method.png ".StorageV1beta1Controller.getStorageV1beta1APIResources") getStorageV1beta1APIResources

> get available resources


```php
function getStorageV1beta1APIResources()
```

#### Example Usage

```php

$result = $storageV1beta1->getStorageV1beta1APIResources();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="list_storage_v1beta1_storage_class"></a>![Method: ](https://apidocs.io/img/method.png ".StorageV1beta1Controller.listStorageV1beta1StorageClass") listStorageV1beta1StorageClass

> list or watch objects of kind StorageClass


```php
function listStorageV1beta1StorageClass(
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 83;
$watch = false;
$pretty = 'pretty';

$result = $storageV1beta1->listStorageV1beta1StorageClass($fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="create_storage_v1beta1_storage_class"></a>![Method: ](https://apidocs.io/img/method.png ".StorageV1beta1Controller.createStorageV1beta1StorageClass") createStorageV1beta1StorageClass

> create a StorageClass


```php
function createStorageV1beta1StorageClass(
        $body,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisStorageV1StorageClass();
$pretty = 'pretty';

$result = $storageV1beta1->createStorageV1beta1StorageClass($body, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_storage_v1beta1_collection_storage_class"></a>![Method: ](https://apidocs.io/img/method.png ".StorageV1beta1Controller.deleteStorageV1beta1CollectionStorageClass") deleteStorageV1beta1CollectionStorageClass

> delete collection of StorageClass


```php
function deleteStorageV1beta1CollectionStorageClass(
        $fieldSelector = null,
        $labelSelector = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 83;
$watch = false;
$pretty = 'pretty';

$result = $storageV1beta1->deleteStorageV1beta1CollectionStorageClass($fieldSelector, $labelSelector, $resourceVersion, $timeoutSeconds, $watch, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_read_storage_v1beta1_storage_class"></a>![Method: ](https://apidocs.io/img/method.png ".StorageV1beta1Controller.getReadStorageV1beta1StorageClass") getReadStorageV1beta1StorageClass

> read the specified StorageClass


```php
function getReadStorageV1beta1StorageClass(
        $name,
        $exact = null,
        $export = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the StorageClass |
| exact |  ``` Optional ```  | Should the export be exact.  Exact export maintains cluster-specific fields like 'Namespace'. |
| export |  ``` Optional ```  | Should this value be exported.  Export strips fields that a user can not specify. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$name = 'name';
$exact = false;
$export = false;
$pretty = 'pretty';

$result = $storageV1beta1->getReadStorageV1beta1StorageClass($name, $exact, $export, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="update_replace_storage_v1beta1_storage_class"></a>![Method: ](https://apidocs.io/img/method.png ".StorageV1beta1Controller.updateReplaceStorageV1beta1StorageClass") updateReplaceStorageV1beta1StorageClass

> replace the specified StorageClass


```php
function updateReplaceStorageV1beta1StorageClass(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the StorageClass |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sKubernetesPkgApisStorageV1StorageClass();
$name = 'name';
$pretty = 'pretty';

$result = $storageV1beta1->updateReplaceStorageV1beta1StorageClass($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="delete_storage_v1beta1_storage_class"></a>![Method: ](https://apidocs.io/img/method.png ".StorageV1beta1Controller.deleteStorageV1beta1StorageClass") deleteStorageV1beta1StorageClass

> delete a StorageClass


```php
function deleteStorageV1beta1StorageClass(
        $body,
        $name,
        $gracePeriodSeconds = null,
        $orphanDependents = null,
        $propagationPolicy = null,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the StorageClass |
| gracePeriodSeconds |  ``` Optional ```  | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. |
| orphanDependents |  ``` Optional ```  | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the "orphan" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. |
| propagationPolicy |  ``` Optional ```  | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = new IoK8sApimachineryPkgApisMetaV1DeleteOptions();
$name = 'name';
$gracePeriodSeconds = 83;
$orphanDependents = false;
$propagationPolicy = 'propagationPolicy';
$pretty = 'pretty';

$result = $storageV1beta1->deleteStorageV1beta1StorageClass($body, $name, $gracePeriodSeconds, $orphanDependents, $propagationPolicy, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="patch_storage_v1beta1_storage_class"></a>![Method: ](https://apidocs.io/img/method.png ".StorageV1beta1Controller.patchStorageV1beta1StorageClass") patchStorageV1beta1StorageClass

> partially update the specified StorageClass


```php
function patchStorageV1beta1StorageClass(
        $body,
        $name,
        $pretty = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| body |  ``` Required ```  | TODO: Add a parameter description |
| name |  ``` Required ```  | name of the StorageClass |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |



#### Example Usage

```php
$body = array('key' => 'value');
$name = 'name';
$pretty = 'pretty';

$result = $storageV1beta1->patchStorageV1beta1StorageClass($body, $name, $pretty);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_storage_v1beta1_storage_class_list"></a>![Method: ](https://apidocs.io/img/method.png ".StorageV1beta1Controller.getWatchStorageV1beta1StorageClassList") getWatchStorageV1beta1StorageClassList

> watch individual changes to a list of StorageClass


```php
function getWatchStorageV1beta1StorageClassList(
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 83;
$watch = false;

$result = $storageV1beta1->getWatchStorageV1beta1StorageClassList($fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_watch_storage_v1beta1_storage_class"></a>![Method: ](https://apidocs.io/img/method.png ".StorageV1beta1Controller.getWatchStorageV1beta1StorageClass") getWatchStorageV1beta1StorageClass

> watch changes to an object of kind StorageClass


```php
function getWatchStorageV1beta1StorageClass(
        $name,
        $fieldSelector = null,
        $labelSelector = null,
        $pretty = null,
        $resourceVersion = null,
        $timeoutSeconds = null,
        $watch = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| name |  ``` Required ```  | name of the StorageClass |
| fieldSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their fields. Defaults to everything. |
| labelSelector |  ``` Optional ```  | A selector to restrict the list of returned objects by their labels. Defaults to everything. |
| pretty |  ``` Optional ```  | If 'true', then the output is pretty printed. |
| resourceVersion |  ``` Optional ```  | When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history. When specified for list: - if unset, then the result is returned from remote storage based on quorum-read flag; - if it's 0, then we simply return what we currently have in cache, no guarantee; - if set to non zero, then the result is at least as fresh as given rv. |
| timeoutSeconds |  ``` Optional ```  | Timeout for the list/watch call. |
| watch |  ``` Optional ```  | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. |



#### Example Usage

```php
$name = 'name';
$fieldSelector = 'fieldSelector';
$labelSelector = 'labelSelector';
$pretty = 'pretty';
$resourceVersion = 'resourceVersion';
$timeoutSeconds = 41;
$watch = false;

$result = $storageV1beta1->getWatchStorageV1beta1StorageClass($name, $fieldSelector, $labelSelector, $pretty, $resourceVersion, $timeoutSeconds, $watch);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="logs_controller"></a>![Class: ](https://apidocs.io/img/class.png ".LogsController") LogsController

### Get singleton instance

The singleton instance of the ``` LogsController ``` class can be accessed from the API Client.

```php
$logs = $client->getLogs();
```

### <a name="get_log_file_list_handler"></a>![Method: ](https://apidocs.io/img/method.png ".LogsController.getLogFileListHandler") getLogFileListHandler

> TODO: Add a method description


```php
function getLogFileListHandler()
```

#### Example Usage

```php

$logs->getLogFileListHandler();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



### <a name="get_log_file_handler"></a>![Method: ](https://apidocs.io/img/method.png ".LogsController.getLogFileHandler") getLogFileHandler

> TODO: Add a method description


```php
function getLogFileHandler($logpath)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| logpath |  ``` Required ```  | path to the log |



#### Example Usage

```php
$logpath = 'logpath';

$logs->getLogFileHandler($logpath);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)

## <a name="version_controller"></a>![Class: ](https://apidocs.io/img/class.png ".VersionController") VersionController

### Get singleton instance

The singleton instance of the ``` VersionController ``` class can be accessed from the API Client.

```php
$version = $client->getVersion();
```

### <a name="get_code_version"></a>![Method: ](https://apidocs.io/img/method.png ".VersionController.getCodeVersion") getCodeVersion

> get the code version


```php
function getCodeVersion()
```

#### Example Usage

```php

$result = $version->getCodeVersion();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 401 | Unauthorized |



[Back to List of Controllers](#list_of_controllers)


