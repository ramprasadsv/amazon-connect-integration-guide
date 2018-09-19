# Using CloudFormation<a name="cloudformation"></a>

Amazon Connect integrations can be packaged as consumable artifacts using AWS CloudFormation\. AWS CloudFormation provides a common language for you to describe and provision all the infrastructure resources in your cloud environment\. CloudFormation allows you to use a simple text file to model and provision, in an automated and secure manner, all the resources needed for your applications across all regions and accounts\. This file serves as the single source of truth for your cloud environment\.

## What is CloudFormation?<a name="whatis"></a>

AWS CloudFormation is a service that helps you model and set up your Amazon Web Services (AWS) resources so that you can spend less time managing those resources and more time focusing on your applications that run in AWS\. For more information about CloudFormation, please review the [documentation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html)\.

## Where do I publish my integration?<a name="channels"></a>

Because Amazon Connect integrations can be complex, there are multiple avenues to publish your integration. The following table identifies these channels and provides a brief description for each. A typical integration may consist of a Marketplace listing where an AMI or SaaS offering can be purchased, a Quick Start for additional dependant services needed for the integration, and a Solution Bundle that comprises the Marketplace and Quick Start as well as a Solution Package that includes additional services\. A comprehensive explanation is available through the  [Amazon Connect ISV Partner On-Boarding Guide](templates/Amazon_Connect_ISV_Partner_Onboarding_v1.0.0.pptx) PowerPoint deck\.


| Channel | Description |
| --- | --- |
|  `AWS Marketplace`  |  Provides a new sales channel for ISVs and Consulting Partners to sell their solutions to AWS customers\.  |
|  `AWS Quick Starts`  |  Built by AWS solutions architects and partners to help you deploy popular solutions on AWS, based on AWS best practices for security and high availability\.  |
|  `AWS Solution Space`  |  Discover scalable and secure solutions that will empower you to achieve your business needs with AWS and AWS Partner Network \(APN\) Partners that have attained AWS Competency designations\.  |

## Selling on Marketplace<a name="marketplace"></a>

AWS Marketplace is a sales channel that makes it easy for AWS Sellers to offer software solutions that run on the AWS cloud\. For more information on selling in the Marketplace, please visit us [here](https://aws.amazon.com/marketplace/management/tour)\.

## Publishing a Quick Start on Amazon Connect Integrations Portal<a name="quickstart"></a>

AWS Quick Starts are built by AWS solutions architects and partners to help you deploy popular solutions on AWS, based on AWS best practices for security and high availability\. AWS Quick Starts offers a general [catalog](https://aws.amazon.com/quickstart) of various reference architectures as well as a dedicated [portal](https://aws.amazon.com/quickstart/connect) for Amazon Connect Integrations\.

### Getting Started<a name="gettingstarted"></a>

Having a thorough understanding of CloudFormation is necessary\. It is recommended that you familiarize yourself with the various [AWS Resource Types](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html) supported by CloudFormation as well referencing the [Intrinsic Functions](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/intrinsic-function-reference.html) available to help you manage your stacks\. A complete [Quick Start Contributor's Guide](https://aws-quickstart.github.io/) is available and describes several options for developing a Quick Start\. These include:
+ [Using an existing Quick Start as a starting point](https://aws-quickstart.github.io/option1.html)
+ [Adding new features or bug fixes for an existing Quick Start](https://aws-quickstart.github.io/option2.html)
+ [Building a new Quick Start](https://aws-quickstart.github.io/option3.html)

### Prerequisites<a name="prerequisites"></a>

Before you start coding, you’ll need to set up your development environment\. You will need to set up the following:

+ A GitHub [account](https://github.com/join?source=header-home).
+ We use SSH authentication in the submodules, so if you want to contribute to the Quick Starts, you must have your public key registered in your GitHub account\.
  - [Adding a new SSH key to your GitHub account](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/)
+ For security, you must enable [two-factor authentication \(2FA\)](https://help.github.com/articles/securing-your-account-with-two-factor-authentication-2fa/) on your account\.
+ Download & install an IDE or editor such as [Atom](https://atom.io/), [Visual Studio Code](https://code.visualstudio.com/Download), [Sublime](http://www.sublimetext.com/), or suitable alternative\.
+ [Set up Git](https://git-scm.com/downloads) on your computer\.

### Relevant Topics<a name="topics"></a>

If you are new to Git or simply need a refresher, please review the list of [commands](https://git-scm.com/doc), as well as the following concepts:

+ [Branching](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)
+ [Submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules) - Quick reference:
  - Adding a Git submodule:

     ```
     git submodule add –b master git@github.com:aws-quickstart/<quickstart-repo-name>.git submodules/<quickstart-repo-name>
     ```
  - Cloning a repository that contains submodules:

     ```
     git clone --recursive git@github.com:aws-quickstart/<quickstart-repo-name>.git
     ```

  - Synchronizing all submodules after a `git pull`:

     ```
     git submodule update --recursive
     ```

  - Update submodules to the latest version:

     ```
     git submodule update --remote --merge
     ```

  - Complete design [reference](https://aws-quickstart.github.io/design.html)\.

### Step by step<a name="steps"></a>

1. Clone [quickstart-examples](https://github.com/aws-quickstart/quickstart-examples)

   ```
   git clone git@github.com:aws-quickstart/quickstart-examples.git
   ```

1. Clone [connect-integration-examples](https://github.com/aws-quickstart/connect-integration-examples)

   ```
   git clone git@github.com:aws-quickstart/connect-integration-examples.git
   ```

1. Clone [taskcat](https://github.com/aws-quickstart/taskcat)

   ```
   git clone git@github.com:aws-quickstart/taskcat.git
   ```

1. Using **quickstart-examples** and **connect-integration-examples** as a reference, begin building your Quick Start
1. Familiarize yourself with the [testing with TaskCat](https://aws-quickstart.github.io/test-debug.html#autotest)
1. Review the Quick Start Support [reference](templates/quickstart_support_ppt.pptx)
1. Once you have tested your Quick Start and validated that there are no CloudFormation validation errors and that all integration components are working without error, you are ready to begin [validation](technical-validation.md)\.

### Quick Reference<a name="reference"></a>

+ When ready, a repository will be created for your integration under the GitHub organization for [AWS Quick Starts](https://github.com/aws-quickstart) and you will be granted READ rights.
  - Your repository will contain **develop** and **master** branches\.
  - Be sure to `git checkout develop` prior to working on your code\.
+ You will need to [fork](https://help.github.com/articles/fork-a-repo) your repository\.
+ Before making any changes to your local, make sure you `git pull` first\.
+ In order to save submit your work to the remote branch, you will need to create a [pull request](https://help.github.com/articles/creating-a-pull-request-from-a-fork)\.
+ Be sure to run **beautycorn** prior to submitting a **pull request**:

  ```
  ../taskcat/beautycorn.py templates/
  ```

+ When working on a Mac, you will need to ensure DS_Store files are not included in the compressed archives for your Lambda functions. To do this, type the following:

  ```
  zip -j functions/packages/integration-test/lambda.zip functions/source/integration-test/* -x "*.DS_Store"
  ```

  Substituting "integration-test" with the appropriate path for your specific integration\.
