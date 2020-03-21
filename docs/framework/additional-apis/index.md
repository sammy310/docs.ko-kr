---
title: 추가 클래스 라이브러리 및 API
ms.date: 11/19/2019
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
ms.topic: conceptual
ms.openlocfilehash: abf7fd20988ebaaaf1a40ccc168c636fd0dacc1d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155910"
---
# <a name="additional-class-libraries-and-apis"></a>추가 클래스 라이브러리 및 API

.NET 프레임워크는 끊임없이 진화하고 있습니다. 플랫폼 간 개발을 개선하고 새로운 기능을 조기에 도입하기 위해 새로운 기능이 OOB(대역 외)에서 릴리스됩니다. 이 항목에서는 설명서를 제공하는 OOB 프로젝트를 나열합니다.  
  
또한 일부 라이브러리는 .NET Framework의 구현이나 특정 플랫폼을 대상으로 합니다. 예를 들어 <xref:System.Text.CodePagesEncodingProvider> 클래스는 .NET Framework를 사용하여 개발된 UWP 앱에서 코드 페이지 인코딩을 사용할 수 있도록 합니다. 이 항목에서는 이러한 라이브러리도 나열됩니다.  
  
## <a name="oob-projects"></a>OOB 프로젝트
  
| Project | Description |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | 해당 내용을 절대로 변경하지 않도록 보장하는 안전한 스레드인 컬렉션을 제공합니다. |
| <xref:System.Net.Http.WinHttpHandler> | Windows의 WinHTTP 인터페이스에 따라 <xref:System.Net.Http.HttpClient> 에 메시지 처리기를 제공합니다. |
| <xref:System.Numerics> | SIMD 하드웨어 기반 가속을 활용할 수 있는 벡터 형식 라이브러리입니다.|
| <xref:System.Threading.Tasks.Dataflow> | TPL 데이터 흐름 라이브러리는 동시성 사용 애플리케이션의 견고성을 높이는 데 도움이 되는 데이터 흐름 구성 요소를 제공합니다. |  

## <a name="platform-specific-libraries"></a>플랫폼별 라이브러리
  
| Project | Description |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <xref:System.Text.EncodingProvider> 유니버설 Windows 플랫폼을 대상으로 하는 앱에서 코드 페이지 인코딩을 사용할 수 있도록 클래스를 확장합니다. |  
  
## <a name="private-apis"></a>전용 API  

이러한 API는 제품 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
* [마이크로소프트.SqlServer.서버.스미오더프로퍼티.아이템 속성](microsoft.sqlserver.server.smiorderproperty.item.md)
* [시스템.예외.준비방법](system.exception.prepforremoting.md)
* [System.Data.SqlType.SqlChars.Stream 속성](system.data.sqltypes.sqlchars.stream.md)
* [System.Data.SqlTypes.SqlStreamChars 생성자](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [System.Data.SqlTypes.SqlStreamChars.CanSeek 속성](system.data.sqltypes.sqlstreamchars.canseek.md)
* [System.Data.SqlTypes.SqlStreamChars.IsNull 속성](system.data.sqltypes.sqlstreamchars.isnull.md)
* [System.Data.SqlTypes.SqlStreamChars.Length 속성](system.data.sqltypes.sqlstreamchars.length.md)
* [System.Data.SqlTypes.SqlStreamChars.닫기 방법](system.data.sqltypes.sqlstreamchars.close.md)
* [System.Data.SqlTypes.SqlStreamChars.Dispose 메서드](system.data.sqltypes.sqlstreamchars.dispose.md)
* [System.Data.SqlTypes.SqlStreamChars.플러시 방법](system.data.sqltypes.sqlstreamchars.flush.md)
* [System.Data.SqlTypes.SqlStreamChars.Read 방법](system.data.sqltypes.sqlstreamchars.read.md)
* [System.Data.SqlTypes.SqlStreamChars.Seek 방법](system.data.sqltypes.sqlstreamchars.seek.md)
* [System.Data.SqlTypes.SqlStreamChars.SetLength 방법](system.data.sqltypes.sqlstreamchars.setlength.md)
* [System.Data.SqlTypes.SqlStreamChars.Write 방법](system.data.sqltypes.sqlstreamchars.write.md)
* [시스템.IO.메모리스트림.내부GetOriginAndLength 방법](system.io.memorystream.internalgetoriginandlength.md)
* [시스템.Net.연결 클래스](connection.md)
* [System.Net.연결.m\_쓰기 목록 필드](m_writelist.md)
* [시스템.Net.연결 그룹 클래스](connectiongroup.md)
* [시스템.Net.연결 그룹.m\_연결 목록 필드](m_connectionlist.md)
* [시스템.Net.연결 스트림.연결 속성](system.net.connectstream.connection.md)
* [시스템.Net.코어응답데이터 클래스](coreresponsedata.md)
* [System.Net.CoreResponseData.m\_응답 헤더 필드](coreresponsedata_m_responseheaders.md)
* [System.Net.CoreResponseData.m\_상태 코드 필드](coreresponsedata_m_statuscode.md)
* [시스템.Net.HttpWebRequest. \_자동 리디렉션 필드](_autoredirects.md)
* [시스템.Net.HttpWebRequest. \_코어응답 필드](httpwebrequest__coreresponse.md)
* [시스템.Net.HttpWebRequest. \_HttpResponse 필드](_httpresponse.md)
* [System.Net.풀드스트림.네트워크스트림 속성](system.net.pooledstream.networkstream.md)
* [시스템.Net.RtcState 클래스](system.net.rtcstate.md)
* [System.Net.ServicePoint.m\_연결 그룹리스트 필드](m_connectiongrouplist.md)
* [시스템.Net.ServicePointManager.s\_서비스 포인트 테이블 필드](s_servicepointtable.md)
* [시스템.넷.TlsStream.m_Worker 필드](system.net.tlsstream.m_worker.md)
* [System.Net.Security.SslState.SslProtocol 속성](system.net.security.sslstate.sslprotocol.md)
* [System.Servicemodel.Channels.Message.BodyToString 방법](system.servicemodel.channels.message.bodytostring.md)
* [System.ServiceModel.Channels.Message.WriteStartHeaders 방법](system.servicemodel.channels.message.writestartheaders.md)
* [System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheck장애인ForTestPurposes 필드](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [시스템.Windows.Forms.디자인.데이터멤버필드에디터 클래스](datamemberfieldeditor-class.md)
* [시스템.Windows.Forms.디자인.데이터멤버리스트편집기 클래스](datamemberlisteditor-class.md)
* [System.Xml.XmlReader.CreateSqlReader 방법](system.xml.xmlreader.createsqlreader.md)
* [Adodb. 연결 인터페이스](adodb.connection.md)
* [Adodb. 이벤트이유 에넘](adodb.eventreasonenum.md)
* [Adodb. 이벤트 상태 열거형](adodb.eventstatusenum.md)
* [stdole. 디스파람스 구조](stdole.dispparams.md)
* [stdole. EXCEPINFO 구조](stdole.excepinfo.md)
* [stdole. IFont.Name 속성](stdole.ifont.name.md)
* [stdole. 아이폰디스프 인터페이스](stdole.ifontdisp.md)
* [stdole. IPicture.핸들 속성](stdole.ipicture.handle.md)
* [stdole. IPictureDisp.핸들 속성](stdole.ipicturedisp.handle.md)
* [stdole. StdFont 인터페이스](stdole.stdfont.md)
* [stdole. StdPicture 인터페이스](stdole.stdpicture.md)
  
## <a name="see-also"></a>참고 항목

* [.NET Framework 및 번외 릴리스](../get-started/the-net-framework-and-out-of-band-releases.md)
