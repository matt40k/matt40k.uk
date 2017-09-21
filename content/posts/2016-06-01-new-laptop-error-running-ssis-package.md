---
title: New laptop, error running SSIS package
author: matt
type: post
date: 2016-06-01T22:06:32+00:00
url: /2016/06/new-laptop-error-running-ssis-package/
categories:
  - Business Intelligence
  - Microsoft
  - SQL Server
  - SSIS

---
So today I went to run a SSIS package on my new laptop and bam, error message.

> Microsoft.SqlServer.Dts.Runtime.DtsRuntimeException: The package failed to load due to error 0xC0011008 &#8220;Error loading from XML. No further detailed error information can be specified for this problem because no Events object was passed where detailed error information can be stored.&#8221;. This occurs when CPackage::LoadFromXML fails.   &#8212;> System.Runtime.InteropServices.COMException: The package failed to load due to error 0xC0011008 &#8220;Error loading from XML. No further detailed error information can be specified for this problem because no Events object was passed where detailed error information can be stored.&#8221;. This occurs when CPackage::LoadFromXML fails.       at Microsoft.SqlServer.Dts.Runtime.Wrapper.IDTSPackagePersist100.LoadPackageFromXML(Object vSource, Boolean vbSourceIsLocation, IDTSEvents100 pEvents)     at Microsoft.SqlServer.Dts.Runtime.Package.LoadFromXML(String packageXml, IDTSEvents events)     &#8212; End of inner exception stack trace &#8212;at Microsoft.SqlServer.Dts.Runtime.Package.LoadFromXML(String packageXml, IDTSEvents events)     at Microsoft.SqlServer.Dts.Runtime.Project.LoadPackage(IProjectStorage storage, Package package, String streamName, IDTSEvents events)     at Microsoft.SqlServer.Dts.Runtime.PackageItem.Load(IDTSEvents events)     at Microsoft.SqlServer.Dts.Runtime.PackageItem.get_Package()     at Microsoft.DataTransformationServices.Project.DataTransformationsProjectBuilder.IncrementalBuildThroughObj(IOutputWindow outputWindow)     at Microsoft.DataTransformationServices.Project.DataTransformationsProjectBuilder.BuildIncremental(IOutputWindow outputWindow)

Translates as I hadn&#8217;t installed the Oracle client and the <a href="https://www.microsoft.com/en-us/download/details.aspx?id=44582" target="_blank" rel="nofollow">Microsoft Connectors v3.0</a>. Speaking of the connectors, the Attunity Oracle adapters are amazing, if your connecting SSIS to Oracle, these are a must (especially as they are free!)
