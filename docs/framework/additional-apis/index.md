---
title: 추가 클래스 라이브러리 및 API
description: 대역 외 (OOB) 프로젝트, 플랫폼별 라이브러리 및 개인 Api를 포함 하 여 .NET의 추가 클래스 라이브러리 및 Api를 살펴보세요.
ms.date: 06/12/2020
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
ms.topic: conceptual
ms.openlocfilehash: 0b888d2f0e80685ba993682b2f3067cf8aee15bc
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989742"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="3e7cd-103">추가 클래스 라이브러리 및 API</span><span class="sxs-lookup"><span data-stu-id="3e7cd-103">Additional class libraries and APIs</span></span>

<span data-ttu-id="3e7cd-104">이 문서에는 대역 외에서 릴리스 되었거나 특정 플랫폼을 대상으로 하거나 전용 또는 내부 유형인 .NET Framework Api가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e7cd-104">This article lists .NET Framework APIs that either were released out of band, target a specific platform, or are private or internal types.</span></span>

## <a name="oob-projects"></a><span data-ttu-id="3e7cd-105">OOB 프로젝트</span><span class="sxs-lookup"><span data-stu-id="3e7cd-105">OOB projects</span></span>

<span data-ttu-id="3e7cd-106">플랫폼 간 개발을 향상 시키고 새로운 기능을 조기에 도입 하려면 일부 .NET Framework 기능이 대역 외 (OOB)에서 출시 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3e7cd-106">To improve cross-platform development and introduce new functionality early, some .NET Framework features were released out of band (OOB).</span></span>

| <span data-ttu-id="3e7cd-107">Project</span><span class="sxs-lookup"><span data-stu-id="3e7cd-107">Project</span></span> | <span data-ttu-id="3e7cd-108">Description</span><span class="sxs-lookup"><span data-stu-id="3e7cd-108">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="3e7cd-109">해당 내용을 절대로 변경하지 않도록 보장하는 안전한 스레드인 컬렉션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3e7cd-109">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="3e7cd-110">Windows의 WinHTTP 인터페이스에 따라 <xref:System.Net.Http.HttpClient> 에 메시지 처리기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3e7cd-110">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="3e7cd-111">SIMD 하드웨어 기반 가속을 활용할 수 있는 벡터 형식 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="3e7cd-111">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>|
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="3e7cd-112">TPL 데이터 흐름 라이브러리는 동시성 사용 애플리케이션의 견고성을 높이는 데 도움이 되는 데이터 흐름 구성 요소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3e7cd-112">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="3e7cd-113">플랫폼별 라이브러리</span><span class="sxs-lookup"><span data-stu-id="3e7cd-113">Platform-specific libraries</span></span>

<span data-ttu-id="3e7cd-114">일부 라이브러리는 특정 플랫폼을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e7cd-114">Some libraries target specific platforms.</span></span> <span data-ttu-id="3e7cd-115">예를 들어 <xref:System.Text.CodePagesEncodingProvider> 클래스는 .NET Framework을 사용 하 여 개발 된 UWP 앱에 사용할 수 있는 코드 페이지 인코딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3e7cd-115">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using .NET Framework.</span></span>
  
| <span data-ttu-id="3e7cd-116">Project</span><span class="sxs-lookup"><span data-stu-id="3e7cd-116">Project</span></span> | <span data-ttu-id="3e7cd-117">Description</span><span class="sxs-lookup"><span data-stu-id="3e7cd-117">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="3e7cd-118">클래스를 확장 <xref:System.Text.EncodingProvider> 하 여 유니버설 Windows 플랫폼를 대상으로 하는 앱에서 코드 페이지 인코딩을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e7cd-118">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="3e7cd-119">전용 API</span><span class="sxs-lookup"><span data-stu-id="3e7cd-119">Private APIs</span></span>  

<span data-ttu-id="3e7cd-120">이러한 Api는 제품 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아니며 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e7cd-120">These APIs support the product infrastructure and are not intended or supported to be used directly from your code.</span></span>  
  
* [<span data-ttu-id="3e7cd-121">SmiOrderProperty 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="3e7cd-121">Microsoft.SqlServer.Server.SmiOrderProperty.Item property</span></span>](microsoft.sqlserver.server.smiorderproperty.item.md)
* [<span data-ttu-id="3e7cd-122">PrepForRemoting 메서드</span><span class="sxs-lookup"><span data-stu-id="3e7cd-122">System.Exception.PrepForRemoting method</span></span>](system.exception.prepforremoting.md)
* [<span data-ttu-id="3e7cd-123">SqlTypes 속성입니다. Stream 속성</span><span class="sxs-lookup"><span data-stu-id="3e7cd-123">System.Data.SqlTypes.SqlChars.Stream property</span></span>](system.data.sqltypes.sqlchars.stream.md)
* [<span data-ttu-id="3e7cd-124">SqlTypes. SqlStreamChars 생성자</span><span class="sxs-lookup"><span data-stu-id="3e7cd-124">System.Data.SqlTypes.SqlStreamChars Constructor</span></span>](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [<span data-ttu-id="3e7cd-125">SqlTypes 속성입니다. .Canseek 속성</span><span class="sxs-lookup"><span data-stu-id="3e7cd-125">System.Data.SqlTypes.SqlStreamChars.CanSeek property</span></span>](system.data.sqltypes.sqlstreamchars.canseek.md)
* [<span data-ttu-id="3e7cd-126">SqlTypes 속성 ()</span><span class="sxs-lookup"><span data-stu-id="3e7cd-126">System.Data.SqlTypes.SqlStreamChars.IsNull property</span></span>](system.data.sqltypes.sqlstreamchars.isnull.md)
* [<span data-ttu-id="3e7cd-127">SqlTypes 속성에 대 한</span><span class="sxs-lookup"><span data-stu-id="3e7cd-127">System.Data.SqlTypes.SqlStreamChars.Length property</span></span>](system.data.sqltypes.sqlstreamchars.length.md)
* [<span data-ttu-id="3e7cd-128">SqlTypes 메서드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="3e7cd-128">System.Data.SqlTypes.SqlStreamChars.Close method</span></span>](system.data.sqltypes.sqlstreamchars.close.md)
* [<span data-ttu-id="3e7cd-129">SqlTypes 메서드를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e7cd-129">System.Data.SqlTypes.SqlStreamChars.Dispose method</span></span>](system.data.sqltypes.sqlstreamchars.dispose.md)
* [<span data-ttu-id="3e7cd-130">SqlTypes 메서드 (메서드)</span><span class="sxs-lookup"><span data-stu-id="3e7cd-130">System.Data.SqlTypes.SqlStreamChars.Flush method</span></span>](system.data.sqltypes.sqlstreamchars.flush.md)
* [<span data-ttu-id="3e7cd-131">SqlTypes 메서드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3e7cd-131">System.Data.SqlTypes.SqlStreamChars.Read method</span></span>](system.data.sqltypes.sqlstreamchars.read.md)
* [<span data-ttu-id="3e7cd-132">SqlTypes 메서드를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e7cd-132">System.Data.SqlTypes.SqlStreamChars.Seek method</span></span>](system.data.sqltypes.sqlstreamchars.seek.md)
* [<span data-ttu-id="3e7cd-133">SqlTypes입니다. SetLength 메서드</span><span class="sxs-lookup"><span data-stu-id="3e7cd-133">System.Data.SqlTypes.SqlStreamChars.SetLength method</span></span>](system.data.sqltypes.sqlstreamchars.setlength.md)
* [<span data-ttu-id="3e7cd-134">SqlTypes 메서드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e7cd-134">System.Data.SqlTypes.SqlStreamChars.Write method</span></span>](system.data.sqltypes.sqlstreamchars.write.md)
* [<span data-ttu-id="3e7cd-135">MemoryStream. InternalGetOriginAndLength 메서드</span><span class="sxs-lookup"><span data-stu-id="3e7cd-135">System.IO.MemoryStream.InternalGetOriginAndLength method</span></span>](system.io.memorystream.internalgetoriginandlength.md)
* [<span data-ttu-id="3e7cd-136">시스템 .Net ComNetOS 클래스</span><span class="sxs-lookup"><span data-stu-id="3e7cd-136">System.Net.ComNetOS class</span></span>](system.net.comnetos.md)
* [<span data-ttu-id="3e7cd-137">시스템 .Net 연결 클래스</span><span class="sxs-lookup"><span data-stu-id="3e7cd-137">System.Net.Connection class</span></span>](connection.md)
* [<span data-ttu-id="3e7cd-138">시스템 .Net 연결 \_ 목록 필드</span><span class="sxs-lookup"><span data-stu-id="3e7cd-138">System.Net.Connection.m\_WriteList field</span></span>](m_writelist.md)
* [<span data-ttu-id="3e7cd-139">시스템 .Net ConnectionGroup 클래스</span><span class="sxs-lookup"><span data-stu-id="3e7cd-139">System.Net.ConnectionGroup class</span></span>](connectiongroup.md)
* [<span data-ttu-id="3e7cd-140">시스템 .Net. ConnectionGroup. m \_ connectiongroup 필드</span><span class="sxs-lookup"><span data-stu-id="3e7cd-140">System.Net.ConnectionGroup.m\_ConnectionList field</span></span>](m_connectionlist.md)
* [<span data-ttu-id="3e7cd-141">시스템 .Net. ConnectStream. 연결 속성</span><span class="sxs-lookup"><span data-stu-id="3e7cd-141">System.Net.ConnectStream.Connection property</span></span>](system.net.connectstream.connection.md)
* [<span data-ttu-id="3e7cd-142">CoreResponseData 클래스</span><span class="sxs-lookup"><span data-stu-id="3e7cd-142">System.Net.CoreResponseData class</span></span>](coreresponsedata.md)
* [<span data-ttu-id="3e7cd-143">CoreResponseData \_ ResponseHeaders 필드</span><span class="sxs-lookup"><span data-stu-id="3e7cd-143">System.Net.CoreResponseData.m\_ResponseHeaders field</span></span>](coreresponsedata_m_responseheaders.md)
* [<span data-ttu-id="3e7cd-144">시스템 CoreResponseData \_ StatusCode 필드</span><span class="sxs-lookup"><span data-stu-id="3e7cd-144">System.Net.CoreResponseData.m\_StatusCode field</span></span>](coreresponsedata_m_statuscode.md)
* [<span data-ttu-id="3e7cd-145">시스템 .Net ExceptionHelper 클래스</span><span class="sxs-lookup"><span data-stu-id="3e7cd-145">System.Net.ExceptionHelper class</span></span>](system.net.exceptionhelper.md)
* [<span data-ttu-id="3e7cd-146">시스템 .Net. HttpStatusDescription 클래스</span><span class="sxs-lookup"><span data-stu-id="3e7cd-146">System.Net.HttpStatusDescription class</span></span>](system.net.httpstatusdescription.md)
* [<span data-ttu-id="3e7cd-147">시스템 .Net HttpWebRequest. \_ AutoRedirects 필드</span><span class="sxs-lookup"><span data-stu-id="3e7cd-147">System.Net.HttpWebRequest.\_AutoRedirects field</span></span>](_autoredirects.md)
* [<span data-ttu-id="3e7cd-148">시스템 .Net HttpWebRequest. \_ CoreResponse 필드</span><span class="sxs-lookup"><span data-stu-id="3e7cd-148">System.Net.HttpWebRequest.\_CoreResponse field</span></span>](httpwebrequest__coreresponse.md)
* [<span data-ttu-id="3e7cd-149">시스템 .Net HttpWebRequest. \_ Httpresponse.cache 필드</span><span class="sxs-lookup"><span data-stu-id="3e7cd-149">System.Net.HttpWebRequest.\_HttpResponse field</span></span>](_httpresponse.md)
* [<span data-ttu-id="3e7cd-150">시스템 .Net 로깅 클래스</span><span class="sxs-lookup"><span data-stu-id="3e7cd-150">System.Net.Logging class</span></span>](system.net.logging.md)
* [<span data-ttu-id="3e7cd-151">MailAddressParser 클래스</span><span class="sxs-lookup"><span data-stu-id="3e7cd-151">System.Net.Mail.MailAddressParser class</span></span>](system.net.mail.mailaddressparser.md)
* [<span data-ttu-id="3e7cd-152">QuotedPairReader 클래스</span><span class="sxs-lookup"><span data-stu-id="3e7cd-152">System.Net.Mail.QuotedPairReader class</span></span>](system.net.mail.quotedpairreader.md)
* [<span data-ttu-id="3e7cd-153">시스템 .Net Mime. MailBnfHelper 클래스</span><span class="sxs-lookup"><span data-stu-id="3e7cd-153">System.Net.Mime.MailBnfHelper class</span></span>](system.net.mime.mailbnfhelper.md)
* [<span data-ttu-id="3e7cd-154">시스템 .Net. PooledStream. NetworkStream 속성</span><span class="sxs-lookup"><span data-stu-id="3e7cd-154">System.Net.PooledStream.NetworkStream property</span></span>](system.net.pooledstream.networkstream.md)
* [<span data-ttu-id="3e7cd-155">RtcState 클래스</span><span class="sxs-lookup"><span data-stu-id="3e7cd-155">System.Net.RtcState class</span></span>](system.net.rtcstate.md)
* [<span data-ttu-id="3e7cd-156">시스템 .Net.. SslState. Sslstate 속성</span><span class="sxs-lookup"><span data-stu-id="3e7cd-156">System.Net.Security.SslState.SslProtocol property</span></span>](system.net.security.sslstate.sslprotocol.md)
* [<span data-ttu-id="3e7cd-157">시스템 .Net. ServicePoint. m \_ ConnectionGroupList 필드</span><span class="sxs-lookup"><span data-stu-id="3e7cd-157">System.Net.ServicePoint.m\_ConnectionGroupList field</span></span>](m_connectiongrouplist.md)
* [<span data-ttu-id="3e7cd-158">시스템 .Net. ServicePointManager 메서드</span><span class="sxs-lookup"><span data-stu-id="3e7cd-158">System.Net.ServicePointManager.CloseConnectionGroups method</span></span>](system.net.servicepointmanager.closeconnectiongroups.md)
* [<span data-ttu-id="3e7cd-159">시스템 .Net. ServicePointManager. s \_ servicepointmanager 필드</span><span class="sxs-lookup"><span data-stu-id="3e7cd-159">System.Net.ServicePointManager.s\_ServicePointTable field</span></span>](s_servicepointtable.md)
* [<span data-ttu-id="3e7cd-160">시스템 .Net. TlsStream m_Worker 필드</span><span class="sxs-lookup"><span data-stu-id="3e7cd-160">System.Net.TlsStream.m_Worker field</span></span>](system.net.tlsstream.m_worker.md)
* [<span data-ttu-id="3e7cd-161">UnsafeNclNativeMethods 클래스</span><span class="sxs-lookup"><span data-stu-id="3e7cd-161">System.Net.UnsafeNclNativeMethods class</span></span>](system.net.unsafenclnativemethods.md)
* [<span data-ttu-id="3e7cd-162">시스템 .Net. WebHeaderCollection. AddInternal 메서드</span><span class="sxs-lookup"><span data-stu-id="3e7cd-162">System.Net.WebHeaderCollection.AddInternal method</span></span>](system.net.webheadercollection.addinternal.md)
* [<span data-ttu-id="3e7cd-163">BodyToString 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="3e7cd-163">System.ServiceModel.Channels.Message.BodyToString method</span></span>](system.servicemodel.channels.message.bodytostring.md)
* [<span data-ttu-id="3e7cd-164">WriteStartHeaders 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="3e7cd-164">System.ServiceModel.Channels.Message.WriteStartHeaders method</span></span>](system.servicemodel.channels.message.writestartheaders.md)
* [<span data-ttu-id="3e7cd-165">IsDebuggerCheckDisabledForTestPurposes 필드를 삭제 합니다. \_</span><span class="sxs-lookup"><span data-stu-id="3e7cd-165">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [<span data-ttu-id="3e7cd-166">DataMemberFieldEditor 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="3e7cd-166">System.Windows.Forms.Design.DataMemberFieldEditor class</span></span>](datamemberfieldeditor-class.md)
* [<span data-ttu-id="3e7cd-167">DataMemberListEditor 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="3e7cd-167">System.Windows.Forms.Design.DataMemberListEditor class</span></span>](datamemberlisteditor-class.md)
* [<span data-ttu-id="3e7cd-168">System.Xml.XmlCreateSqlReader 메서드</span><span class="sxs-lookup"><span data-stu-id="3e7cd-168">System.Xml.XmlReader.CreateSqlReader method</span></span>](system.xml.xmlreader.createsqlreader.md)
* [<span data-ttu-id="3e7cd-169">adodb.dll. 연결 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3e7cd-169">adodb.Connection interface</span></span>](adodb.connection.md)
* [<span data-ttu-id="3e7cd-170">adodb.dll. EventReason 열거형</span><span class="sxs-lookup"><span data-stu-id="3e7cd-170">adodb.EventReason enum</span></span>](adodb.eventreasonenum.md)
* [<span data-ttu-id="3e7cd-171">adodb.dll. EventStatus 열거형</span><span class="sxs-lookup"><span data-stu-id="3e7cd-171">adodb.EventStatus enum</span></span>](adodb.eventstatusenum.md)
* [<span data-ttu-id="3e7cd-172">stdole. DISPPARAMS 구조체</span><span class="sxs-lookup"><span data-stu-id="3e7cd-172">stdole.DISPPARAMS Structure</span></span>](stdole.dispparams.md)
* [<span data-ttu-id="3e7cd-173">stdole. EXCEPINFO 구조체</span><span class="sxs-lookup"><span data-stu-id="3e7cd-173">stdole.EXCEPINFO Structure</span></span>](stdole.excepinfo.md)
* [<span data-ttu-id="3e7cd-174">stdole. IFont.Name 속성</span><span class="sxs-lookup"><span data-stu-id="3e7cd-174">stdole.IFont.Name property</span></span>](stdole.ifont.name.md)
* [<span data-ttu-id="3e7cd-175">stdole. IFontDisp 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3e7cd-175">stdole.IFontDisp interface</span></span>](stdole.ifontdisp.md)
* [<span data-ttu-id="3e7cd-176">stdole. IPicture 속성</span><span class="sxs-lookup"><span data-stu-id="3e7cd-176">stdole.IPicture.Handle property</span></span>](stdole.ipicture.handle.md)
* [<span data-ttu-id="3e7cd-177">stdole. IPictureDisp 속성</span><span class="sxs-lookup"><span data-stu-id="3e7cd-177">stdole.IPictureDisp.Handle property</span></span>](stdole.ipicturedisp.handle.md)
* [<span data-ttu-id="3e7cd-178">stdole. StdFont 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3e7cd-178">stdole.StdFont interface</span></span>](stdole.stdfont.md)
* [<span data-ttu-id="3e7cd-179">stdole. StdPicture 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3e7cd-179">stdole.StdPicture interface</span></span>](stdole.stdpicture.md)
  
## <a name="see-also"></a><span data-ttu-id="3e7cd-180">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3e7cd-180">See also</span></span>

* [<span data-ttu-id="3e7cd-181">.NET Framework 및 번외 릴리스</span><span class="sxs-lookup"><span data-stu-id="3e7cd-181">.NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
