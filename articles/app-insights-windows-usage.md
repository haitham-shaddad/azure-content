<properties 
	pageTitle="Monitor usage in Windows Store and Phone apps with Application Insights" 
	description="Analyze usage of your Windows device app with Application Insights." 
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
	ms.date="02/28/2015" 
	ms.author="awills"/>

#  Monitor usage in Windows Store and Windows Phone apps with Application Insights

*Application Insights is in preview.*

Learn how many users you have, and which pages they're looking at in your app. Application Insights provides you with that data out of the box. And by inserting a few lines of code in your app, you can learn more about the paths users take through your app and what they achieve with it.

If you haven't done this already, add [Application Insights to your app project][windows], and republish it. 


## <a name="usage"></a>Track usage

From the Overview timeline, click through Users and Sessions charts to see more detailed analytics.


![](./media/appinsights/appinsights-d018-oview.png)

* **Users** are tracked anonymously, so the same user on different devices would be counted twice.
* A **session** is counted when the app is suspended (for more than a brief interval, to avoid counting accidental suspensions).

#### Segmentation

Segment a chart to get a breakdown by a variety of criteria. For example, to see how many users are using each version of your app, open the Users chart and segment by Application Version: 

![On the users chart, switch on Segmenting and choose Application version](./media/appinsights/appinsights-d25-usage.png)


#### Page views

To discover the paths that users follow through your app, insert [page view telemetry][api] into  your code:

    var telemetry = new TelemetryClient();
    telemetry.TrackPageView("GameReviewPage");

See the results on the page views chart, and by opening its details:

![](./media/appinsights/appinsights-d27-pages.png)

Click through any page to see the details of specific occurrences.

#### Custom events

By inserting code to send custom events from your app, you can track your users' behavior and the usage of specific features and scenarios. 

For example:

    telemetry.TrackEvent("GameOver");

The data will appear in the Custom Events grid. You can either see an aggregated view in Metrics Explorer, or click through any event to see specific occurrences.

![](./media/appinsights/appinsights-d28-events.png)


You can add string and numeric properties to any event.


    // Set up some properties:
    var properties = new Dictionary <string, string> 
       {{"Game", currentGame.Name}, {"Difficulty", currentGame.Difficulty}};
    var measurements = new Dictionary <string, double>
       {{"Score", currentGame.Score}, {"Opponents", currentGame.OpponentCount}};

    // Send the event:
    telemetry.TrackEvent("GameOver", properties, measurements);


Click through any occurrence to see its detailed properties, including those you have defined.


![](./media/appinsights/appinsights-d29-eventProps.png)

See [API reference][api] for more about custom events.



## <a name="debug"></a>Debug vs Release mode

#### Debug

If you build in debug mode, events are sent as soon as they are generated. If you lose internet connectivity and then exit the app before regaining connectivity, offline telemetry is discarded.

#### Release

If you build in release configuration, events are stored in the device and sent when the application resumes. Data is also sent on the applicationâ€™s first use. If there is no internet connectivity upon startup, previous telemetry as well as telemetry for the current lifecycle is stored and sent on the next resume.

## <a name="next"></a>Next steps

[Know your users][knowUsers]

[Learn more about Metrics Explorer][metrics]


[Troubleshooting][qna]




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

