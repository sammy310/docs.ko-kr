---
title: 추가 클래스 라이브러리 및 API
ms.date: 10/09/2019
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
author: mairaw
ms.author: mairaw
ms.topic: conceptual
ms.openlocfilehash: b869ca2f5e17db9a204a8b757b5e24ebb209d7c5
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395654"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="60955-102">추가 클래스 라이브러리 및 API</span><span class="sxs-lookup"><span data-stu-id="60955-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="60955-103">.NET Framework 지속적으로 진화 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60955-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="60955-104">플랫폼 간 개발을 개선 하 고 새로운 기능을 조기에 도입 하기 위해 새로운 기능이 대역 외 (OOB) 출시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60955-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="60955-105">이 항목에서는 설명서를 제공하는 OOB 프로젝트를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="60955-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="60955-106">또한 일부 라이브러리는 .NET Framework의 구현이나 특정 플랫폼을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="60955-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="60955-107">예를 들어 <xref:System.Text.CodePagesEncodingProvider> 클래스는 .NET Framework를 사용 하 여 개발 된 UWP 앱에서 코드 페이지 인코딩을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="60955-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="60955-108">이 항목에서는 이러한 라이브러리도 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="60955-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="60955-109">OOB 프로젝트</span><span class="sxs-lookup"><span data-stu-id="60955-109">OOB projects</span></span>
  
| <span data-ttu-id="60955-110">프로젝트</span><span class="sxs-lookup"><span data-stu-id="60955-110">Project</span></span> | <span data-ttu-id="60955-111">설명</span><span class="sxs-lookup"><span data-stu-id="60955-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="60955-112">해당 내용을 절대로 변경하지 않도록 보장하는 안전한 스레드인 컬렉션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="60955-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="60955-113">Windows의 WinHTTP 인터페이스에 따라 <xref:System.Net.Http.HttpClient> 에 메시지 처리기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="60955-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="60955-114">SIMD 하드웨어 기반 가속을 활용할 수 있는 벡터 형식 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="60955-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="60955-115">TPL 데이터 흐름 라이브러리는 동시성 사용 애플리케이션의 견고성을 높이는 데 도움이 되는 데이터 흐름 구성 요소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="60955-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="60955-116">플랫폼별 라이브러리</span><span class="sxs-lookup"><span data-stu-id="60955-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="60955-117">프로젝트</span><span class="sxs-lookup"><span data-stu-id="60955-117">Project</span></span> | <span data-ttu-id="60955-118">설명</span><span class="sxs-lookup"><span data-stu-id="60955-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="60955-119">@No__t-0 클래스를 확장 하 여 유니버설 Windows 플랫폼를 대상으로 하는 앱에서 코드 페이지 인코딩을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="60955-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="60955-120">전용 API</span><span class="sxs-lookup"><span data-stu-id="60955-120">Private APIs</span></span>  

<span data-ttu-id="60955-121">이러한 API는 제품 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="60955-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
* [<span data-ttu-id="60955-122">SmiOrderProperty 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="60955-122">Microsoft.SqlServer.Server.SmiOrderProperty.Item Property</span></span>](microsoft.sqlserver.server.smiorderproperty.item.md)
* [<span data-ttu-id="60955-123">PrepForRemoting 메서드</span><span class="sxs-lookup"><span data-stu-id="60955-123">System.Exception.PrepForRemoting Method</span></span>](system.exception.prepforremoting.md)
* [<span data-ttu-id="60955-124">SqlTypes 속성입니다. Stream 속성</span><span class="sxs-lookup"><span data-stu-id="60955-124">System.Data.SqlTypes.SqlChars.Stream Property</span></span>](system.data.sqltypes.sqlchars.stream.md)
* [<span data-ttu-id="60955-125">SqlTypes. SqlStreamChars 생성자</span><span class="sxs-lookup"><span data-stu-id="60955-125">System.Data.SqlTypes.SqlStreamChars Constructor</span></span>](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [<span data-ttu-id="60955-126">SqlTypes 속성입니다. .Canseek 속성</span><span class="sxs-lookup"><span data-stu-id="60955-126">System.Data.SqlTypes.SqlStreamChars.CanSeek Property</span></span>](system.data.sqltypes.sqlstreamchars.canseek.md)
* [<span data-ttu-id="60955-127">SqlTypes 속성 ()</span><span class="sxs-lookup"><span data-stu-id="60955-127">System.Data.SqlTypes.SqlStreamChars.IsNull Property</span></span>](system.data.sqltypes.sqlstreamchars.isnull.md)
* [<span data-ttu-id="60955-128">SqlTypes 속성에 대 한</span><span class="sxs-lookup"><span data-stu-id="60955-128">System.Data.SqlTypes.SqlStreamChars.Length Property</span></span>](system.data.sqltypes.sqlstreamchars.length.md)
* [<span data-ttu-id="60955-129">SqlTypes 메서드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="60955-129">System.Data.SqlTypes.SqlStreamChars.Close Method</span></span>](system.data.sqltypes.sqlstreamchars.close.md)
* [<span data-ttu-id="60955-130">SqlTypes 메서드를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="60955-130">System.Data.SqlTypes.SqlStreamChars.Dispose Method</span></span>](system.data.sqltypes.sqlstreamchars.dispose.md)
* [<span data-ttu-id="60955-131">SqlTypes 메서드 (메서드)</span><span class="sxs-lookup"><span data-stu-id="60955-131">System.Data.SqlTypes.SqlStreamChars.Flush Method</span></span>](system.data.sqltypes.sqlstreamchars.flush.md)
* [<span data-ttu-id="60955-132">SqlTypes 메서드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="60955-132">System.Data.SqlTypes.SqlStreamChars.Read Method</span></span>](system.data.sqltypes.sqlstreamchars.read.md)
* [<span data-ttu-id="60955-133">SqlTypes 메서드를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="60955-133">System.Data.SqlTypes.SqlStreamChars.Seek Method</span></span>](system.data.sqltypes.sqlstreamchars.seek.md)
* [<span data-ttu-id="60955-134">SqlTypes입니다. SetLength 메서드</span><span class="sxs-lookup"><span data-stu-id="60955-134">System.Data.SqlTypes.SqlStreamChars.SetLength Method</span></span>](system.data.sqltypes.sqlstreamchars.setlength.md)
* [<span data-ttu-id="60955-135">SqlTypes 메서드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="60955-135">System.Data.SqlTypes.SqlStreamChars.Write Method</span></span>](system.data.sqltypes.sqlstreamchars.write.md)
* [<span data-ttu-id="60955-136">시스템 .Net 연결 클래스</span><span class="sxs-lookup"><span data-stu-id="60955-136">System.Net.Connection Class</span></span>](connection.md)
* [<span data-ttu-id="60955-137">시스템 .Net. 연결. m @ no__t-1WriteList 필드</span><span class="sxs-lookup"><span data-stu-id="60955-137">System.Net.Connection.m\_WriteList Field</span></span>](m_writelist.md)
* [<span data-ttu-id="60955-138">시스템 .Net ConnectionGroup 클래스</span><span class="sxs-lookup"><span data-stu-id="60955-138">System.Net.ConnectionGroup Class</span></span>](connectiongroup.md)
* [<span data-ttu-id="60955-139">시스템 .Net. ConnectionGroup. m @ no__t-1ConnectionList 필드</span><span class="sxs-lookup"><span data-stu-id="60955-139">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](m_connectionlist.md)
* [<span data-ttu-id="60955-140">CoreResponseData 클래스</span><span class="sxs-lookup"><span data-stu-id="60955-140">System.Net.CoreResponseData Class</span></span>](coreresponsedata.md)
* [<span data-ttu-id="60955-141">CoreResponseData @ no__t-1ResponseHeaders 필드</span><span class="sxs-lookup"><span data-stu-id="60955-141">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](coreresponsedata_m_responseheaders.md)
* [<span data-ttu-id="60955-142">시스템 .Net. CoreResponseData @ no__t-1StatusCode 필드</span><span class="sxs-lookup"><span data-stu-id="60955-142">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](coreresponsedata_m_statuscode.md)
* [<span data-ttu-id="60955-143">1AutoRedirects 필드 (필드) @no__t</span><span class="sxs-lookup"><span data-stu-id="60955-143">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](_autoredirects.md)
* [<span data-ttu-id="60955-144">1CoreResponse 필드 (필드) @no__t</span><span class="sxs-lookup"><span data-stu-id="60955-144">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](httpwebrequest__coreresponse.md)
* [<span data-ttu-id="60955-145">1HttpResponse 필드 (필드) @no__t</span><span class="sxs-lookup"><span data-stu-id="60955-145">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](_httpresponse.md)
* [<span data-ttu-id="60955-146">시스템 .Net. ServicePoint. m @ no__t-1ConnectionGroupList 필드</span><span class="sxs-lookup"><span data-stu-id="60955-146">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](m_connectiongrouplist.md)
* [<span data-ttu-id="60955-147">시스템 .Net. ServicePointManager. s @ no__t-1ServicePointTable 필드</span><span class="sxs-lookup"><span data-stu-id="60955-147">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](s_servicepointtable.md)
* [<span data-ttu-id="60955-148">1isDebuggerCheckDisabledForTestPurposes @ no__t-s i m 진단. s</span><span class="sxs-lookup"><span data-stu-id="60955-148">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [<span data-ttu-id="60955-149">DataMemberFieldEditor 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="60955-149">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](datamemberfieldeditor-class.md)
* [<span data-ttu-id="60955-150">DataMemberListEditor 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="60955-150">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](datamemberlisteditor-class.md)
* [<span data-ttu-id="60955-151">adodb.dll. 연결 인터페이스</span><span class="sxs-lookup"><span data-stu-id="60955-151">adodb.Connection Interface</span></span>](adodb.connection.md)
* [<span data-ttu-id="60955-152">adodb.dll. EventReason 열거형</span><span class="sxs-lookup"><span data-stu-id="60955-152">adodb.EventReason Enum</span></span>](adodb.eventreasonenum.md)
* [<span data-ttu-id="60955-153">adodb.dll. EventStatus 열거형</span><span class="sxs-lookup"><span data-stu-id="60955-153">adodb.EventStatus Enum</span></span>](adodb.eventstatusenum.md)
* [<span data-ttu-id="60955-154">stdole. DISPPARAMS 구조체</span><span class="sxs-lookup"><span data-stu-id="60955-154">stdole.DISPPARAMS Structure</span></span>](stdole.dispparams.md)
* [<span data-ttu-id="60955-155">stdole. EXCEPINFO 구조체</span><span class="sxs-lookup"><span data-stu-id="60955-155">stdole.EXCEPINFO Structure</span></span>](stdole.excepinfo.md)
* [<span data-ttu-id="60955-156">stdole. IFont.Name 속성</span><span class="sxs-lookup"><span data-stu-id="60955-156">stdole.IFont.Name Property</span></span>](stdole.ifont.name.md)
* [<span data-ttu-id="60955-157">stdole. IFontDisp 인터페이스</span><span class="sxs-lookup"><span data-stu-id="60955-157">stdole.IFontDisp Interface</span></span>](stdole.ifontdisp.md)
* [<span data-ttu-id="60955-158">stdole. IPicture 속성</span><span class="sxs-lookup"><span data-stu-id="60955-158">stdole.IPicture.Handle Property</span></span>](stdole.ipicture.handle.md)
* [<span data-ttu-id="60955-159">stdole. IPictureDisp 속성</span><span class="sxs-lookup"><span data-stu-id="60955-159">stdole.IPictureDisp.Handle Property</span></span>](stdole.ipicturedisp.handle.md)
* [<span data-ttu-id="60955-160">stdole. StdFont 인터페이스</span><span class="sxs-lookup"><span data-stu-id="60955-160">stdole.StdFont Interface</span></span>](stdole.stdfont.md)
* [<span data-ttu-id="60955-161">stdole. StdPicture 인터페이스</span><span class="sxs-lookup"><span data-stu-id="60955-161">stdole.StdPicture Interface</span></span>](stdole.stdpicture.md)
  
## <a name="see-also"></a><span data-ttu-id="60955-162">참조</span><span class="sxs-lookup"><span data-stu-id="60955-162">See also</span></span>

* [<span data-ttu-id="60955-163">.NET Framework 및 번외 릴리스</span><span class="sxs-lookup"><span data-stu-id="60955-163">The .NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
