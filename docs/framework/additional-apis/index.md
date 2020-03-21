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
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="ca354-102">추가 클래스 라이브러리 및 API</span><span class="sxs-lookup"><span data-stu-id="ca354-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="ca354-103">.NET 프레임워크는 끊임없이 진화하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca354-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="ca354-104">플랫폼 간 개발을 개선하고 새로운 기능을 조기에 도입하기 위해 새로운 기능이 OOB(대역 외)에서 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca354-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="ca354-105">이 항목에서는 설명서를 제공하는 OOB 프로젝트를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="ca354-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="ca354-106">또한 일부 라이브러리는 .NET Framework의 구현이나 특정 플랫폼을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca354-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="ca354-107">예를 들어 <xref:System.Text.CodePagesEncodingProvider> 클래스는 .NET Framework를 사용하여 개발된 UWP 앱에서 코드 페이지 인코딩을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca354-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="ca354-108">이 항목에서는 이러한 라이브러리도 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca354-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="ca354-109">OOB 프로젝트</span><span class="sxs-lookup"><span data-stu-id="ca354-109">OOB projects</span></span>
  
| <span data-ttu-id="ca354-110">Project</span><span class="sxs-lookup"><span data-stu-id="ca354-110">Project</span></span> | <span data-ttu-id="ca354-111">Description</span><span class="sxs-lookup"><span data-stu-id="ca354-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="ca354-112">해당 내용을 절대로 변경하지 않도록 보장하는 안전한 스레드인 컬렉션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ca354-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="ca354-113">Windows의 WinHTTP 인터페이스에 따라 <xref:System.Net.Http.HttpClient> 에 메시지 처리기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ca354-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="ca354-114">SIMD 하드웨어 기반 가속을 활용할 수 있는 벡터 형식 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="ca354-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>|
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="ca354-115">TPL 데이터 흐름 라이브러리는 동시성 사용 애플리케이션의 견고성을 높이는 데 도움이 되는 데이터 흐름 구성 요소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ca354-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="ca354-116">플랫폼별 라이브러리</span><span class="sxs-lookup"><span data-stu-id="ca354-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="ca354-117">Project</span><span class="sxs-lookup"><span data-stu-id="ca354-117">Project</span></span> | <span data-ttu-id="ca354-118">Description</span><span class="sxs-lookup"><span data-stu-id="ca354-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="ca354-119"><xref:System.Text.EncodingProvider> 유니버설 Windows 플랫폼을 대상으로 하는 앱에서 코드 페이지 인코딩을 사용할 수 있도록 클래스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="ca354-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="ca354-120">전용 API</span><span class="sxs-lookup"><span data-stu-id="ca354-120">Private APIs</span></span>  

<span data-ttu-id="ca354-121">이러한 API는 제품 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca354-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
* [<span data-ttu-id="ca354-122">마이크로소프트.SqlServer.서버.스미오더프로퍼티.아이템 속성</span><span class="sxs-lookup"><span data-stu-id="ca354-122">Microsoft.SqlServer.Server.SmiOrderProperty.Item Property</span></span>](microsoft.sqlserver.server.smiorderproperty.item.md)
* [<span data-ttu-id="ca354-123">시스템.예외.준비방법</span><span class="sxs-lookup"><span data-stu-id="ca354-123">System.Exception.PrepForRemoting Method</span></span>](system.exception.prepforremoting.md)
* [<span data-ttu-id="ca354-124">System.Data.SqlType.SqlChars.Stream 속성</span><span class="sxs-lookup"><span data-stu-id="ca354-124">System.Data.SqlTypes.SqlChars.Stream Property</span></span>](system.data.sqltypes.sqlchars.stream.md)
* [<span data-ttu-id="ca354-125">System.Data.SqlTypes.SqlStreamChars 생성자</span><span class="sxs-lookup"><span data-stu-id="ca354-125">System.Data.SqlTypes.SqlStreamChars Constructor</span></span>](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [<span data-ttu-id="ca354-126">System.Data.SqlTypes.SqlStreamChars.CanSeek 속성</span><span class="sxs-lookup"><span data-stu-id="ca354-126">System.Data.SqlTypes.SqlStreamChars.CanSeek Property</span></span>](system.data.sqltypes.sqlstreamchars.canseek.md)
* [<span data-ttu-id="ca354-127">System.Data.SqlTypes.SqlStreamChars.IsNull 속성</span><span class="sxs-lookup"><span data-stu-id="ca354-127">System.Data.SqlTypes.SqlStreamChars.IsNull Property</span></span>](system.data.sqltypes.sqlstreamchars.isnull.md)
* [<span data-ttu-id="ca354-128">System.Data.SqlTypes.SqlStreamChars.Length 속성</span><span class="sxs-lookup"><span data-stu-id="ca354-128">System.Data.SqlTypes.SqlStreamChars.Length Property</span></span>](system.data.sqltypes.sqlstreamchars.length.md)
* [<span data-ttu-id="ca354-129">System.Data.SqlTypes.SqlStreamChars.닫기 방법</span><span class="sxs-lookup"><span data-stu-id="ca354-129">System.Data.SqlTypes.SqlStreamChars.Close Method</span></span>](system.data.sqltypes.sqlstreamchars.close.md)
* [<span data-ttu-id="ca354-130">System.Data.SqlTypes.SqlStreamChars.Dispose 메서드</span><span class="sxs-lookup"><span data-stu-id="ca354-130">System.Data.SqlTypes.SqlStreamChars.Dispose Method</span></span>](system.data.sqltypes.sqlstreamchars.dispose.md)
* [<span data-ttu-id="ca354-131">System.Data.SqlTypes.SqlStreamChars.플러시 방법</span><span class="sxs-lookup"><span data-stu-id="ca354-131">System.Data.SqlTypes.SqlStreamChars.Flush Method</span></span>](system.data.sqltypes.sqlstreamchars.flush.md)
* [<span data-ttu-id="ca354-132">System.Data.SqlTypes.SqlStreamChars.Read 방법</span><span class="sxs-lookup"><span data-stu-id="ca354-132">System.Data.SqlTypes.SqlStreamChars.Read Method</span></span>](system.data.sqltypes.sqlstreamchars.read.md)
* [<span data-ttu-id="ca354-133">System.Data.SqlTypes.SqlStreamChars.Seek 방법</span><span class="sxs-lookup"><span data-stu-id="ca354-133">System.Data.SqlTypes.SqlStreamChars.Seek Method</span></span>](system.data.sqltypes.sqlstreamchars.seek.md)
* [<span data-ttu-id="ca354-134">System.Data.SqlTypes.SqlStreamChars.SetLength 방법</span><span class="sxs-lookup"><span data-stu-id="ca354-134">System.Data.SqlTypes.SqlStreamChars.SetLength Method</span></span>](system.data.sqltypes.sqlstreamchars.setlength.md)
* [<span data-ttu-id="ca354-135">System.Data.SqlTypes.SqlStreamChars.Write 방법</span><span class="sxs-lookup"><span data-stu-id="ca354-135">System.Data.SqlTypes.SqlStreamChars.Write Method</span></span>](system.data.sqltypes.sqlstreamchars.write.md)
* [<span data-ttu-id="ca354-136">시스템.IO.메모리스트림.내부GetOriginAndLength 방법</span><span class="sxs-lookup"><span data-stu-id="ca354-136">System.IO.MemoryStream.InternalGetOriginAndLength Method</span></span>](system.io.memorystream.internalgetoriginandlength.md)
* [<span data-ttu-id="ca354-137">시스템.Net.연결 클래스</span><span class="sxs-lookup"><span data-stu-id="ca354-137">System.Net.Connection Class</span></span>](connection.md)
* [<span data-ttu-id="ca354-138">System.Net.연결.m\_쓰기 목록 필드</span><span class="sxs-lookup"><span data-stu-id="ca354-138">System.Net.Connection.m\_WriteList Field</span></span>](m_writelist.md)
* [<span data-ttu-id="ca354-139">시스템.Net.연결 그룹 클래스</span><span class="sxs-lookup"><span data-stu-id="ca354-139">System.Net.ConnectionGroup Class</span></span>](connectiongroup.md)
* [<span data-ttu-id="ca354-140">시스템.Net.연결 그룹.m\_연결 목록 필드</span><span class="sxs-lookup"><span data-stu-id="ca354-140">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](m_connectionlist.md)
* [<span data-ttu-id="ca354-141">시스템.Net.연결 스트림.연결 속성</span><span class="sxs-lookup"><span data-stu-id="ca354-141">System.Net.ConnectStream.Connection Property</span></span>](system.net.connectstream.connection.md)
* [<span data-ttu-id="ca354-142">시스템.Net.코어응답데이터 클래스</span><span class="sxs-lookup"><span data-stu-id="ca354-142">System.Net.CoreResponseData Class</span></span>](coreresponsedata.md)
* [<span data-ttu-id="ca354-143">System.Net.CoreResponseData.m\_응답 헤더 필드</span><span class="sxs-lookup"><span data-stu-id="ca354-143">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](coreresponsedata_m_responseheaders.md)
* [<span data-ttu-id="ca354-144">System.Net.CoreResponseData.m\_상태 코드 필드</span><span class="sxs-lookup"><span data-stu-id="ca354-144">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](coreresponsedata_m_statuscode.md)
* [<span data-ttu-id="ca354-145">시스템.Net.HttpWebRequest. \_자동 리디렉션 필드</span><span class="sxs-lookup"><span data-stu-id="ca354-145">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](_autoredirects.md)
* [<span data-ttu-id="ca354-146">시스템.Net.HttpWebRequest. \_코어응답 필드</span><span class="sxs-lookup"><span data-stu-id="ca354-146">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](httpwebrequest__coreresponse.md)
* [<span data-ttu-id="ca354-147">시스템.Net.HttpWebRequest. \_HttpResponse 필드</span><span class="sxs-lookup"><span data-stu-id="ca354-147">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](_httpresponse.md)
* [<span data-ttu-id="ca354-148">System.Net.풀드스트림.네트워크스트림 속성</span><span class="sxs-lookup"><span data-stu-id="ca354-148">System.Net.PooledStream.NetworkStream Property</span></span>](system.net.pooledstream.networkstream.md)
* [<span data-ttu-id="ca354-149">시스템.Net.RtcState 클래스</span><span class="sxs-lookup"><span data-stu-id="ca354-149">System.Net.RtcState class</span></span>](system.net.rtcstate.md)
* [<span data-ttu-id="ca354-150">System.Net.ServicePoint.m\_연결 그룹리스트 필드</span><span class="sxs-lookup"><span data-stu-id="ca354-150">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](m_connectiongrouplist.md)
* [<span data-ttu-id="ca354-151">시스템.Net.ServicePointManager.s\_서비스 포인트 테이블 필드</span><span class="sxs-lookup"><span data-stu-id="ca354-151">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](s_servicepointtable.md)
* [<span data-ttu-id="ca354-152">시스템.넷.TlsStream.m_Worker 필드</span><span class="sxs-lookup"><span data-stu-id="ca354-152">System.Net.TlsStream.m_Worker Field</span></span>](system.net.tlsstream.m_worker.md)
* [<span data-ttu-id="ca354-153">System.Net.Security.SslState.SslProtocol 속성</span><span class="sxs-lookup"><span data-stu-id="ca354-153">System.Net.Security.SslState.SslProtocol Property</span></span>](system.net.security.sslstate.sslprotocol.md)
* [<span data-ttu-id="ca354-154">System.Servicemodel.Channels.Message.BodyToString 방법</span><span class="sxs-lookup"><span data-stu-id="ca354-154">System.ServiceModel.Channels.Message.BodyToString Method</span></span>](system.servicemodel.channels.message.bodytostring.md)
* [<span data-ttu-id="ca354-155">System.ServiceModel.Channels.Message.WriteStartHeaders 방법</span><span class="sxs-lookup"><span data-stu-id="ca354-155">System.ServiceModel.Channels.Message.WriteStartHeaders Method</span></span>](system.servicemodel.channels.message.writestartheaders.md)
* [<span data-ttu-id="ca354-156">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheck장애인ForTestPurposes 필드</span><span class="sxs-lookup"><span data-stu-id="ca354-156">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [<span data-ttu-id="ca354-157">시스템.Windows.Forms.디자인.데이터멤버필드에디터 클래스</span><span class="sxs-lookup"><span data-stu-id="ca354-157">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](datamemberfieldeditor-class.md)
* [<span data-ttu-id="ca354-158">시스템.Windows.Forms.디자인.데이터멤버리스트편집기 클래스</span><span class="sxs-lookup"><span data-stu-id="ca354-158">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](datamemberlisteditor-class.md)
* [<span data-ttu-id="ca354-159">System.Xml.XmlReader.CreateSqlReader 방법</span><span class="sxs-lookup"><span data-stu-id="ca354-159">System.Xml.XmlReader.CreateSqlReader Method</span></span>](system.xml.xmlreader.createsqlreader.md)
* [<span data-ttu-id="ca354-160">Adodb. 연결 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca354-160">adodb.Connection Interface</span></span>](adodb.connection.md)
* [<span data-ttu-id="ca354-161">Adodb. 이벤트이유 에넘</span><span class="sxs-lookup"><span data-stu-id="ca354-161">adodb.EventReason Enum</span></span>](adodb.eventreasonenum.md)
* [<span data-ttu-id="ca354-162">Adodb. 이벤트 상태 열거형</span><span class="sxs-lookup"><span data-stu-id="ca354-162">adodb.EventStatus Enum</span></span>](adodb.eventstatusenum.md)
* [<span data-ttu-id="ca354-163">stdole. 디스파람스 구조</span><span class="sxs-lookup"><span data-stu-id="ca354-163">stdole.DISPPARAMS Structure</span></span>](stdole.dispparams.md)
* [<span data-ttu-id="ca354-164">stdole. EXCEPINFO 구조</span><span class="sxs-lookup"><span data-stu-id="ca354-164">stdole.EXCEPINFO Structure</span></span>](stdole.excepinfo.md)
* [<span data-ttu-id="ca354-165">stdole. IFont.Name 속성</span><span class="sxs-lookup"><span data-stu-id="ca354-165">stdole.IFont.Name Property</span></span>](stdole.ifont.name.md)
* [<span data-ttu-id="ca354-166">stdole. 아이폰디스프 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca354-166">stdole.IFontDisp Interface</span></span>](stdole.ifontdisp.md)
* [<span data-ttu-id="ca354-167">stdole. IPicture.핸들 속성</span><span class="sxs-lookup"><span data-stu-id="ca354-167">stdole.IPicture.Handle Property</span></span>](stdole.ipicture.handle.md)
* [<span data-ttu-id="ca354-168">stdole. IPictureDisp.핸들 속성</span><span class="sxs-lookup"><span data-stu-id="ca354-168">stdole.IPictureDisp.Handle Property</span></span>](stdole.ipicturedisp.handle.md)
* [<span data-ttu-id="ca354-169">stdole. StdFont 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca354-169">stdole.StdFont Interface</span></span>](stdole.stdfont.md)
* [<span data-ttu-id="ca354-170">stdole. StdPicture 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca354-170">stdole.StdPicture Interface</span></span>](stdole.stdpicture.md)
  
## <a name="see-also"></a><span data-ttu-id="ca354-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca354-171">See also</span></span>

* [<span data-ttu-id="ca354-172">.NET Framework 및 번외 릴리스</span><span class="sxs-lookup"><span data-stu-id="ca354-172">The .NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
