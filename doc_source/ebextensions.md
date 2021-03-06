# Advanced Environment Customization with Configuration Files \(`.ebextensions`\)<a name="ebextensions"></a>

You can add AWS Elastic Beanstalk configuration files \(`.ebextensions`\) to your web application's source code to configure your environment and customize the AWS resources that it contains\. Configuration files are YAML formatted documents with a `.config` file extension that you place in a folder named `.ebextensions` and deploy in your application source bundle\.

**Tip**  
When you are developing or testing new configuration files, launch a clean environment running the default application and deploy to that\. Poorly formatted configuration files will cause a new environment launch to fail unrecoverably\.

The `option_settings` section of a configuration file defines values for [configuration options](command-options.md)\. Configuration options let you configure your Elastic Beanstalk environment, the AWS resources in it, and the software that runs your application\. Configuration files are only one of several ways to set configuration options\.

The [`Resources` section](environment-resources.md) lets you further customize the resources in your application's environment, and define additional AWS resources beyond the functionality provided by configuration options\. You can add and configure any resources supported by AWS CloudFormation, which Elastic Beanstalk uses to create environments\.

The other sections of a configuration file \(`packages`, `sources`, `files`, `users`, `groups`, `commands`, `container_commands`, and `services`\) let you configure the EC2 instances that are launched in your environment\. Whenever a server is launched in your environment, Elastic Beanstalk runs the operations defined in these sections to prepare the operating system and storage system for your application\.

**Requirements**

+ **Location** – Place all of your configuration files in a single folder, named `.ebextensions`, in the root of your source bundle\. Folders starting with a dot can be hidden by file browsers, so make sure that the folder is added when you create your source bundle\. See [Create an Application Source Bundle](applications-sourcebundle.md) for instructions\.

+ **Naming** – Configuration files must have the `.config` file extension\.

+ **Formatting** – Configuration files must conform to YAML formatting requirements\. Always use spaces to indent and don't use the same key twice in the same file\.
**Warning**  
If you use a key \(for example, `option_settings`\) twice in the same configuration file, one of the sections will be dropped\. Combine duplicate sections into a single section, or place them in separate configuration files\.

  For more information about YAML, see [YAML Ain't Markup Language \(YAML™\) Version 1\.1](http://yaml.org/spec/current.html)\.

The process for deploying varies slightly depending on the client that you use to manage your environments\. See the following sections for details:

+ [Elastic Beanstalk Console](environment-configuration-methods-during.md#configuration-options-during-console-ebextensions)

+ [EB CLI](environment-configuration-methods-during.md#configuration-options-during-ebcli-ebextensions)

+ [AWS CLI](environment-configuration-methods-during.md#configuration-options-during-awscli-ebextensions)


+ [Option Settings](ebextensions-optionsettings.md)
+ [Customizing Software on Linux Servers](customize-containers-ec2.md)
+ [Customizing Software on Windows Servers](customize-containers-windows-ec2.md)
+ [Adding and Customizing Elastic Beanstalk Environment Resources](environment-resources.md)