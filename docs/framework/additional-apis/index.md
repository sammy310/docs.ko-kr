---
title: 추가 클래스 라이브러리 및 API
description: 대역 외 (OOB) 프로젝트, 플랫폼별 라이브러리 및 개인 Api를 포함 하 여 .NET의 추가 클래스 라이브러리 및 Api를 살펴보세요.
ms.date: 08/11/2020
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
ms.topic: conceptual
ms.openlocfilehash: c6404df5d4f0be381bc0a9c1924fcf82cf078306
ms.sourcegitcommit: 70d6a7e4f7187cbfa332f0f8be76566f7828cfcd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/11/2020
ms.locfileid: "88075477"
---
# <a name="additional-class-libraries-and-apis"></a>추가 클래스 라이브러리 및 API

이 문서에는 대역 외에서 릴리스 되었거나 특정 플랫폼을 대상으로 하거나 전용 또는 내부 유형인 .NET Framework Api가 나열 되어 있습니다.

## <a name="oob-projects"></a>OOB 프로젝트

플랫폼 간 개발을 향상 시키고 새로운 기능을 조기에 도입 하려면 일부 .NET Framework 기능이 대역 외 (OOB)에서 출시 되었습니다.

| 프로젝트 | 설명 |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | 해당 내용을 절대로 변경하지 않도록 보장하는 안전한 스레드인 컬렉션을 제공합니다. |
| <xref:System.Net.Http.WinHttpHandler> | Windows의 WinHTTP 인터페이스에 따라 <xref:System.Net.Http.HttpClient> 에 메시지 처리기를 제공합니다. |
| <xref:System.Numerics> | SIMD 하드웨어 기반 가속을 활용할 수 있는 벡터 형식 라이브러리입니다.|
| <xref:System.Threading.Tasks.Dataflow> | TPL 데이터 흐름 라이브러리는 동시성 사용 애플리케이션의 견고성을 높이는 데 도움이 되는 데이터 흐름 구성 요소를 제공합니다. |  

## <a name="platform-specific-libraries"></a>플랫폼별 라이브러리

일부 라이브러리는 특정 플랫폼을 대상으로 합니다. 예를 들어 <xref:System.Text.CodePagesEncodingProvider> 클래스는 .NET Framework을 사용 하 여 개발 된 UWP 앱에 사용할 수 있는 코드 페이지 인코딩을 만듭니다.
  
| 프로젝트 | 설명 |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | 클래스를 확장 <xref:System.Text.EncodingProvider> 하 여 유니버설 Windows 플랫폼를 대상으로 하는 앱에서 코드 페이지 인코딩을 사용할 수 있도록 합니다. |  
  
## <a name="private-apis"></a>전용 API  

이러한 Api는 제품 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아니며 지원 되지 않습니다.  
  
* [SmiOrderProperty 속성입니다.](microsoft.sqlserver.server.smiorderproperty.item.md)
* [PrepForRemoting 메서드](system.exception.prepforremoting.md)
* [SqlTypes 속성입니다. Stream 속성](system.data.sqltypes.sqlchars.stream.md)
* [SqlTypes. SqlStreamChars 생성자](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [SqlTypes 속성입니다. .Canseek 속성](system.data.sqltypes.sqlstreamchars.canseek.md)
* [SqlTypes 속성 ()](system.data.sqltypes.sqlstreamchars.isnull.md)
* [SqlTypes 속성에 대 한](system.data.sqltypes.sqlstreamchars.length.md)
* [SqlTypes 메서드를 닫습니다.](system.data.sqltypes.sqlstreamchars.close.md)
* [SqlTypes 메서드를 삭제 합니다.](system.data.sqltypes.sqlstreamchars.dispose.md)
* [SqlTypes 메서드 (메서드)](system.data.sqltypes.sqlstreamchars.flush.md)
* [SqlTypes 메서드를 참조 하세요.](system.data.sqltypes.sqlstreamchars.read.md)
* [SqlTypes 메서드를 검색 합니다.](system.data.sqltypes.sqlstreamchars.seek.md)
* [SqlTypes입니다. SetLength 메서드](system.data.sqltypes.sqlstreamchars.setlength.md)
* [SqlTypes 메서드를 작성 합니다.](system.data.sqltypes.sqlstreamchars.write.md)
* [MemoryStream. InternalGetOriginAndLength 메서드](system.io.memorystream.internalgetoriginandlength.md)
* [시스템 .Net ComNetOS 클래스](system.net.comnetos.md)
* [시스템 .Net 연결 클래스](connection.md)
* [시스템 .Net 연결 \_ 목록 필드](m_writelist.md)
* [시스템 .Net ConnectionGroup 클래스](connectiongroup.md)
* [시스템 .Net. ConnectionGroup. m \_ connectiongroup 필드](m_connectionlist.md)
* [시스템 .Net. ConnectStream. 연결 속성](system.net.connectstream.connection.md)
* [CoreResponseData 클래스](coreresponsedata.md)
* [CoreResponseData \_ ResponseHeaders 필드](coreresponsedata_m_responseheaders.md)
* [시스템 CoreResponseData \_ StatusCode 필드](coreresponsedata_m_statuscode.md)
* [시스템 .Net ExceptionHelper 클래스](system.net.exceptionhelper.md)
* [시스템 .Net. HttpStatusDescription 클래스](system.net.httpstatusdescription.md)
* [시스템 .Net HttpWebRequest. \_ AutoRedirects 필드](_autoredirects.md)
* [시스템 .Net HttpWebRequest. \_ CoreResponse 필드](httpwebrequest__coreresponse.md)
* [시스템 .Net HttpWebRequest. \_ Httpresponse.cache 필드](_httpresponse.md)
* [시스템 .Net 로깅 클래스](system.net.logging.md)
* [MailAddressParser 클래스](system.net.mail.mailaddressparser.md)
* [QuotedPairReader 클래스](system.net.mail.quotedpairreader.md)
* [시스템 .Net Mime. MailBnfHelper 클래스](system.net.mime.mailbnfhelper.md)
* [시스템 .Net. PooledStream. NetworkStream 속성](system.net.pooledstream.networkstream.md)
* [RtcState 클래스](system.net.rtcstate.md)
* [시스템 .Net.. SslState. Sslstate 속성](system.net.security.sslstate.sslprotocol.md)
* [시스템 .Net. ServicePoint. m \_ ConnectionGroupList 필드](m_connectiongrouplist.md)
* [시스템 .Net. ServicePointManager 메서드](system.net.servicepointmanager.closeconnectiongroups.md)
* [시스템 .Net. ServicePointManager. s \_ servicepointmanager 필드](s_servicepointtable.md)
* [시스템 .Net. TlsStream m_Worker 필드](system.net.tlsstream.m_worker.md)
* [UnsafeNclNativeMethods 클래스](system.net.unsafenclnativemethods.md)
* [시스템 .Net. WebHeaderCollection. AddInternal 메서드](system.net.webheadercollection.addinternal.md)
* [BodyToString 메서드입니다.](system.servicemodel.channels.message.bodytostring.md)
* [WriteStartHeaders 메서드입니다.](system.servicemodel.channels.message.writestartheaders.md)
* [ControlBuilderInterceptor 클래스입니다.](controlbuilderinterceptor-class.md)
* [IsDebuggerCheckDisabledForTestPurposes 필드를 삭제 합니다. \_](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [DataMemberFieldEditor 클래스입니다.](datamemberfieldeditor-class.md)
* [DataMemberListEditor 클래스입니다.](datamemberlisteditor-class.md)
* [System.Xml.XmlCreateSqlReader 메서드](system.xml.xmlreader.createsqlreader.md)
* [adodb.dll. 연결 인터페이스](adodb.connection.md)
* [adodb.dll. EventReason 열거형](adodb.eventreasonenum.md)
* [adodb.dll. EventStatus 열거형](adodb.eventstatusenum.md)
* [stdole. DISPPARAMS 구조체](stdole.dispparams.md)
* [stdole. EXCEPINFO 구조체](stdole.excepinfo.md)
* [stdole. IFont.Name 속성](stdole.ifont.name.md)
* [stdole. IFontDisp 인터페이스](stdole.ifontdisp.md)
* [stdole. IPicture 속성](stdole.ipicture.handle.md)
* [stdole. IPictureDisp 속성](stdole.ipicturedisp.handle.md)
* [stdole. StdFont 인터페이스](stdole.stdfont.md)
* [stdole. StdPicture 인터페이스](stdole.stdpicture.md)
  
## <a name="see-also"></a>참고 항목

* [.NET Framework 및 번외 릴리스](../get-started/the-net-framework-and-out-of-band-releases.md)
