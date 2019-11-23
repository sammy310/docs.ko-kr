---
title: 추가 클래스 라이브러리 및 API
ms.date: 11/19/2019
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
author: mairaw
ms.author: mairaw
ms.topic: conceptual
ms.openlocfilehash: e1e2af584c73b1c0b2548cdd3fcbd8517dfa330d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429343"
---
# <a name="additional-class-libraries-and-apis"></a>추가 클래스 라이브러리 및 API

The .NET Framework is constantly evolving. To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB). 이 항목에서는 설명서를 제공하는 OOB 프로젝트를 나열합니다.  
  
또한 일부 라이브러리는 .NET Framework의 구현이나 특정 플랫폼을 대상으로 합니다. For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework. 이 항목에서는 이러한 라이브러리도 나열됩니다.  
  
## <a name="oob-projects"></a>OOB 프로젝트
  
| 프로젝트 | 설명 |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | 해당 내용을 절대로 변경하지 않도록 보장하는 안전한 스레드인 컬렉션을 제공합니다. |
| <xref:System.Net.Http.WinHttpHandler> | Windows의 WinHTTP 인터페이스에 따라 <xref:System.Net.Http.HttpClient> 에 메시지 처리기를 제공합니다. |
| <xref:System.Numerics> | SIMD 하드웨어 기반 가속을 활용할 수 있는 벡터 형식 라이브러리입니다.| 
| <xref:System.Threading.Tasks.Dataflow> | TPL 데이터 흐름 라이브러리는 동시성 사용 애플리케이션의 견고성을 높이는 데 도움이 되는 데이터 흐름 구성 요소를 제공합니다. |  

## <a name="platform-specific-libraries"></a>플랫폼별 라이브러리
  
| 프로젝트 | 설명 |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform. |  
  
## <a name="private-apis"></a>전용 API  

이러한 API는 제품 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
* [Microsoft.SqlServer.Server.SmiOrderProperty.Item Property](microsoft.sqlserver.server.smiorderproperty.item.md)
* [System.Exception.PrepForRemoting Method](system.exception.prepforremoting.md)
* [System.Data.SqlTypes.SqlChars.Stream Property](system.data.sqltypes.sqlchars.stream.md)
* [System.Data.SqlTypes.SqlStreamChars Constructor](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [System.Data.SqlTypes.SqlStreamChars.CanSeek Property](system.data.sqltypes.sqlstreamchars.canseek.md)
* [System.Data.SqlTypes.SqlStreamChars.IsNull Property](system.data.sqltypes.sqlstreamchars.isnull.md)
* [System.Data.SqlTypes.SqlStreamChars.Length Property](system.data.sqltypes.sqlstreamchars.length.md)
* [System.Data.SqlTypes.SqlStreamChars.Close Method](system.data.sqltypes.sqlstreamchars.close.md)
* [System.Data.SqlTypes.SqlStreamChars.Dispose Method](system.data.sqltypes.sqlstreamchars.dispose.md)
* [System.Data.SqlTypes.SqlStreamChars.Flush Method](system.data.sqltypes.sqlstreamchars.flush.md)
* [System.Data.SqlTypes.SqlStreamChars.Read Method](system.data.sqltypes.sqlstreamchars.read.md)
* [System.Data.SqlTypes.SqlStreamChars.Seek Method](system.data.sqltypes.sqlstreamchars.seek.md)
* [System.Data.SqlTypes.SqlStreamChars.SetLength Method](system.data.sqltypes.sqlstreamchars.setlength.md)
* [System.Data.SqlTypes.SqlStreamChars.Write Method](system.data.sqltypes.sqlstreamchars.write.md)
* [System.IO.MemoryStream.InternalGetOriginAndLength Method](system.io.memorystream.internalgetoriginandlength.md)
* [System.Net.Connection Class](connection.md)
* [System.Net.Connection.m\_WriteList Field](m_writelist.md)
* [System.Net.ConnectionGroup Class](connectiongroup.md)
* [System.Net.ConnectionGroup.m\_ConnectionList Field](m_connectionlist.md)
* [System.Net.ConnectStream.Connection Property](system.net.connectstream.connection.md)
* [System.Net.CoreResponseData Class](coreresponsedata.md)
* [System.Net.CoreResponseData.m\_ResponseHeaders Field](coreresponsedata_m_responseheaders.md)
* [System.Net.CoreResponseData.m\_StatusCode Field](coreresponsedata_m_statuscode.md)
* [System.Net.HttpWebRequest.\_AutoRedirects Field](_autoredirects.md)
* [System.Net.HttpWebRequest.\_CoreResponse Field](httpwebrequest__coreresponse.md)
* [System.Net.HttpWebRequest.\_HttpResponse Field](_httpresponse.md)
* [System.Net.PooledStream.NetworkStream Property](system.net.pooledstream.networkstream.md)
* [System.Net.RtcState class](system.net.rtcstate.md)
* [System.Net.ServicePoint.m\_ConnectionGroupList Field](m_connectiongrouplist.md)
* [System.Net.ServicePointManager.s\_ServicePointTable Field](s_servicepointtable.md)
* [System.Net.TlsStream.m_Worker Field](system.net.tlsstream.m_worker.md)
* [System.Net.Security.SslState.SslProtocol Property](system.net.security.sslstate.sslprotocol.md)
* [System.ServiceModel.Channels.Message.BodyToString Method](system.servicemodel.channels.message.bodytostring.md)
* [System.ServiceModel.Channels.Message.WriteStartHeaders Method](system.servicemodel.channels.message.writestartheaders.md)
* [System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [System.Windows.Forms.Design.DataMemberFieldEditor Class](datamemberfieldeditor-class.md)
* [System.Windows.Forms.Design.DataMemberListEditor Class](datamemberlisteditor-class.md)
* [System.Xml.XmlReader.CreateSqlReader Method](system.xml.xmlreader.createsqlreader.md)
* [adodb.Connection Interface](adodb.connection.md)
* [adodb.EventReason Enum](adodb.eventreasonenum.md)
* [adodb.EventStatus Enum](adodb.eventstatusenum.md)
* [stdole.DISPPARAMS Structure](stdole.dispparams.md)
* [stdole.EXCEPINFO Structure](stdole.excepinfo.md)
* [stdole.IFont.Name Property](stdole.ifont.name.md)
* [stdole.IFontDisp Interface](stdole.ifontdisp.md)
* [stdole.IPicture.Handle Property](stdole.ipicture.handle.md)
* [stdole.IPictureDisp.Handle Property](stdole.ipicturedisp.handle.md)
* [stdole.StdFont Interface](stdole.stdfont.md)
* [stdole.StdPicture Interface](stdole.stdpicture.md)
  
## <a name="see-also"></a>참조

* [.NET Framework 및 번외 릴리스](../get-started/the-net-framework-and-out-of-band-releases.md)
