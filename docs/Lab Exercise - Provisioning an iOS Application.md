# FMX Mobile Application Development

## **Lab Exercise**: Provisioning an iOS Application

Apple requires you to *provision* your applications and iOS devices to
be able to [[run your applications on those
devices]{.underline}](http://docwiki.embarcadero.com/RADStudio/en/Running_Your_iOS_Application_on_an_iOS_Device),
to [[distribute your application *ad
hoc*]{.underline}](http://docwiki.embarcadero.com/RADStudio/en/Deploying_Your_iOS_Application_for_Ad_hoc_Distribution),
or to [[submit your application to the App
Store]{.underline}](http://docwiki.embarcadero.com/RADStudio/en/Deploying_Your_iOS_Application_for_Submission_to_the_App_Store).

## Prerequisites

Before you can provision your application you must:

- Be part of the Apple Developer Program. [[Join the Apple Developer
  Program]{.underline}](http://docwiki.embarcadero.com/RADStudio/en/Joining_the_Apple_Developer_Program) if
  you have not joined the program yet.

- [[Acquire an iOS developer
  certificate]{.underline}](http://docwiki.embarcadero.com/RADStudio/en/Acquiring_an_iOS_Developer_Certificate).

## Creating an App ID for Your Application

Apple requires you to create an [[App
ID]{.underline}](https://developer.apple.com/library/ios/#documentation/General/Conceptual/DevPedia-CocoaCore/AppID.html) for
each one of your applications, or for a group of applications. The App
ID is a unique identifier for your applications. See the [[Apple
documentation]{.underline}](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/MaintainingProfiles/MaintainingProfiles.html) to
learn how to create an app ID for your new application.

You must update the value of the CFBundleIdentifier field of
the [**[Version
Info]{.underline}**](http://docwiki.embarcadero.com/RADStudio/Tokyo/en/Version_Info) page
of your project for iOS platforms so that it contains the App ID of your
application, to do this:

1.  Go to **Project \> Options \> Version Info**

2.  Update the CFBundleIdentifier field to include the Bundle ID such as
    for example:

**com.mycompany.\$(ModuleName)**

To be able to add [**[iOS In-App
Purchase]{.underline}**](http://docwiki.embarcadero.com/RADStudio/en/Using_the_iOS_In-App_Purchase_Service) support
to your application, use an explicit app ID that is specific to a single
application; for example: com.mycompany.myapp. You cannot use a wildcard
app ID such as com.mycompany.\*. That is to say, myapp name should
coincide with the App ID name of
the [[itunesconnect]{.underline}](https://itunesconnect.apple.com/) entry
of your application.

## Creating and Installing Your Provisioning Profiles

**Apple requires you to create a *provisioning profile* for each App
ID,** which you can use to provision your applications that use that App
ID. For each App ID, you may require the following provisioning
profiles:

- A **development provisioning profile**, necessary to sign applications
  for debug, so that you can [[run your application on your iOS
  devices]{.underline}](http://docwiki.embarcadero.com/RADStudio/en/Running_Your_iOS_Application_on_an_iOS_Device) (**Development** platform
  configuration)

- A **distribution provisioning profile** to sign applications for [[ad
  hoc
  distribution]{.underline}](http://docwiki.embarcadero.com/RADStudio/en/Deploying_Your_iOS_Application_for_Ad_hoc_Distribution) of
  your application (**Ad hoc** platform configuration)

- A distribution provisioning profile to sign applications
  for [[submission to the App
  Store]{.underline}](http://docwiki.embarcadero.com/RADStudio/en/Deploying_Your_iOS_Application_for_Submission_to_the_App_Store) (**Application
  Store** platform configuration)

See the [[Apple
documentation]{.underline}](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/SubmittingYourApp/SubmittingYourApp.html) to
learn how to create these provisioning profiles and how to install them
on your iOS devices.

From RAD Studio, the selected provisioning profile is automatically
installed on the target device. You only need to select the device on
the [[Project
Manager]{.underline}](http://docwiki.embarcadero.com/RADStudio/en/Project_Manager) and
deploy the project.

## Configuring Your Provisioning Profiles on RAD Studio

With your application open in RAD Studio, select **Project \> Options
\> [[Provisioning]{.underline}](http://docwiki.embarcadero.com/RADStudio/en/Provisioning_Page)**.
Here you must [[provide your provisioning
data]{.underline}](http://docwiki.embarcadero.com/RADStudio/en/Completing_the_Provisioning_Page) for
the different iOS device platform configurations: **Development**, **Ad
hoc**, and **Application Store**.

**Note:** Platform configurations for the **iOS Device - 32
bit** and **iOS Device - 64 bit** target platforms are not shared. For
example, your changes to **iOS Device - 32 bit - Development** do not
affect **iOS Device - 64 bit - Development**; if you want to change
the **Development** iOS platform configuration you must change
both **iOS Device - 32 bit - Development** and **iOS Device - 64 bit -
Development**.

When you configure your provisioning data for
the **Development** platform configuration, select in **Target** the
build configuration that you want to use to debug your application (for
example, **Debug**).\
When you configure your provisioning data for the **Ad
hoc** and **Application Store** platform configurations, select
in **Target** the build configuration that you want to use to deploy
your application (for example, **Release**).

**Note:** You can configure your *default provisioning
profiles* from **Tools \> Options \> Environment Options
\> [[Provisioning]{.underline}](http://docwiki.embarcadero.com/RADStudio/en/Provisioning_Page)**.
If you do not configure your provisioning profiles for your new project,
RAD Studio uses the default provisioning profiles instead.
