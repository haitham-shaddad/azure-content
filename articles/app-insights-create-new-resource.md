<properties 
	pageTitle="Create a new Application Insights resource" 
	description="Set up for a new application and get a new instrumentation key. Application Insights monitors the performance and usage of live applications." 
	services="application-insights" 
    documentationCenter=""
	authors="alancameronwills" 
	manager="ronmart"/>

<tags 
	ms.service="application-insights" 
	ms.workload="tbd" 
	ms.tgt_pltfrm="ibiza" 
	ms.devlang="na" 
	ms.topic="article" 
	ms.date="04/13/2015" 
	ms.author="awills"/>

# Create a new Application Insights resource


[AZURE.INCLUDE [app-insights-selector-get-started](../includes/app-insights-selector-get-started.md)]

Visual Studio Application Insights displays data about your application in a Microsoft Azure *resource*. Creating a new resource is therefore part of [setting up Application Insights to monitor a new application][start]. In many cases, this can be done automatically by the IDE, and that's the recommended way where it's available. But in some cases, you create a resource manually.

After you have created the resource, you get its instrumentation key and use that to configure the SDK in the application. This sends the telemetry to the resource.

## Sign up to Microsoft Azure

If you haven't got a [Microsoft account, get one now](http://live.com). (If you use services like Outlook.com, OneDrive, Windows Phone, or XBox Live, you already have a Microsoft account.)

You'll also need a subscription to [Microsoft Azure](http://azure.com). If your team or organization has an Azure subscription, the owner can add you to it, using your Windows Live ID.

Or you can create a new subscription. The free trial lets you try everything in Azure. After the trial period expires, you might find the pay-as-you-go subscription appropriate, as you won't be charged for free services. 

When you've got access to a subscription, login to Application Insights at [http://portal.azure.com](http://portal.azure.com), and use your Live ID to login.


## Create an Application Insights resource
  

In the [portal.azure.com](https://portal.azure.com), add an Application Insights resource:

![Click New, Application Insights](./media/app-insights-windows-get-started/01-new.png)


* **Application type** affects what you see on the overview blade and the properties available in [metric explorer][metrics]. If you don't see your type of app, choose one of the web types for web pages, and one of the phone types for other devices.
* **Resource group** is a convenience for managing properties like access control. If you have already created other Azure resources, you can choose to put this new resource in the same group.
* **Subscription** is your payment account in Azure.
* **Location** is where we keep your data. Currently it can't be changed.
* **Add to startboard** puts a quick-access tile for your resource on your Azure Home page. Recommended.

When your app has been created, a new blade opens. This is where you'll see performance and usage data about your app. 

To get back to it next time you login to Azure, look for your app's quick-start tile on the start board (home screen). Or click Browse to find it.


## Copy  the Instrumentation Key.


You'll need this shortly, to direct the data from the SDK in your app to the resource you just created.

![Click Properties, select the key, and press ctrl+C](./media/app-insights-windows-get-started/02-props.png)

## Configure your SDK

Use the instrumentation key to configure [the SDK that you install in your application][start].

This step depends heavily on the type of application you are working with. 

In some cases, you install standard modules that send telemetry without you having to write any code. In all cases, you can [use the API][api] to send your own telemetry.

## <a name="monitor"></a>See telemetry data

Close the quick start blade to return to your application blade in the Azure portal.

Click the Search tile to see [Diagnostic Search][diagnostic], where the first events will appear. 

Click Refresh after a few seconds if you're expecting more data.




<!--Link references-->

[alerts]: app-insightss-alerts.md
[android]: https://github.com/Microsoft/AppInsights-Android
[api]: app-insights-custom-events-metrics-api.md
[apiproperties]: app-insights-custom-events-metrics-api.md#properties
[apiref]: http://msdn.microsoft.com/library/azure/dn887942.aspx
[availability]: app-insights-monitor-web-app-availability.md
[azure]: insights-perf-analytics.md
[azure-availability]: insights-create-web-tests.md
[azure-usage]: insights-usage-analytics.md
[azurediagnostic]: insights-how-to-use-diagnostics.md
[client]: app-insights-web-track-usage.md
[config]: app-insights-configuration-with-applicationinsights-config.md
[data]: app-insights-data-retention-privacy.md
[desktop]: app-insights-windows-desktop.md
[detect]: app-insights-detect-triage-diagnose.md
[diagnostic]: app-insights-diagnostic-search.md
[eclipse]: app-insights-java-eclipse.md
[exceptions]: app-insights-web-failures-exceptions.md
[export]: app-insights-export-telemetry.md
[exportcode]: app-insights-code-sample-export-telemetry-sql-database.md
[greenbrown]: app-insights-start-monitoring-app-health-usage.md
[java]: app-insights-java-get-started.md
[javalogs]: app-insights-java-trace-logs.md
[javareqs]: app-insights-java-track-http-requests.md
[knowUsers]: app-insights-overview-usage.md
[metrics]: app-insights-metrics-explorer.md
[netlogs]: app-insights-asp-net-trace-logs.md
[new]: app-insights-create-new-resource.md
[older]: http://www.visualstudio.com/get-started/get-usage-data-vs
[perf]: app-insights-web-monitor-performance.md
[platforms]: app-insights-platforms.md
[portal]: http://portal.azure.com/
[qna]: app-insights-troubleshoot-faq.md
[redfield]: app-insights-monitor-performance-live-website-now.md
[roles]: app-insights-role-based-access-control.md
[start]: app-insights-get-started.md
[trace]: app-insights-search-diagnostic-logs.md
[track]: app-insights-custom-events-metrics-api.md
[usage]: app-insights-web-track-usage.md
[windows]: app-insights-windows-get-started.md
[windowsCrash]: app-insights-windows-crashes.md
[windowsUsage]: app-insights-windows-usage.md

