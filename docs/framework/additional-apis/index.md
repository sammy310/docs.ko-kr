---
title: 추가 클래스 라이브러리 및 API
ms.date: 01/29/2018
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
author: mairaw
ms.author: mairaw
ms.topic: conceptual
ms.openlocfilehash: 0aed6f32bbd3ffdc9446e9d17be2d90c62444ee1
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053251"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="52886-102">추가 클래스 라이브러리 및 API</span><span class="sxs-lookup"><span data-stu-id="52886-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="52886-103">.NET Framework 지속적으로 진화 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52886-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="52886-104">플랫폼 간 개발을 개선 하 고 새로운 기능을 조기에 도입 하기 위해 새로운 기능이 대역 외 (OOB) 출시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52886-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="52886-105">이 항목에서는 설명서를 제공하는 OOB 프로젝트를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="52886-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="52886-106">또한 일부 라이브러리는 .NET Framework의 구현이나 특정 플랫폼을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="52886-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="52886-107">예를 들어 클래스 <xref:System.Text.CodePagesEncodingProvider> 는 .NET Framework을 사용 하 여 개발 된 UWP 앱에서 코드 페이지 인코딩을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="52886-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="52886-108">이 항목에서는 이러한 라이브러리도 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="52886-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="52886-109">OOB 프로젝트</span><span class="sxs-lookup"><span data-stu-id="52886-109">OOB projects</span></span>
  
| <span data-ttu-id="52886-110">프로젝트</span><span class="sxs-lookup"><span data-stu-id="52886-110">Project</span></span> | <span data-ttu-id="52886-111">설명</span><span class="sxs-lookup"><span data-stu-id="52886-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="52886-112">해당 내용을 절대로 변경하지 않도록 보장하는 안전한 스레드인 컬렉션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="52886-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="52886-113">Windows의 WinHTTP 인터페이스에 따라 <xref:System.Net.Http.HttpClient> 에 메시지 처리기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="52886-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="52886-114">SIMD 하드웨어 기반 가속을 활용할 수 있는 벡터 형식 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="52886-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="52886-115">TPL 데이터 흐름 라이브러리는 동시성 사용 애플리케이션의 견고성을 높이는 데 도움이 되는 데이터 흐름 구성 요소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="52886-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="52886-116">플랫폼별 라이브러리</span><span class="sxs-lookup"><span data-stu-id="52886-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="52886-117">프로젝트</span><span class="sxs-lookup"><span data-stu-id="52886-117">Project</span></span> | <span data-ttu-id="52886-118">설명</span><span class="sxs-lookup"><span data-stu-id="52886-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="52886-119"><xref:System.Text.EncodingProvider> 클래스를 확장 하 여 유니버설 Windows 플랫폼를 대상으로 하는 앱에서 코드 페이지 인코딩을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="52886-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="52886-120">전용 API</span><span class="sxs-lookup"><span data-stu-id="52886-120">Private APIs</span></span>  

<span data-ttu-id="52886-121">이러한 API는 제품 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52886-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="52886-122">API 이름</span><span class="sxs-lookup"><span data-stu-id="52886-122">API Name</span></span> |
| -------- |
| [<span data-ttu-id="52886-123">시스템 .Net 연결 클래스</span><span class="sxs-lookup"><span data-stu-id="52886-123">System.Net.Connection Class</span></span>](connection.md) |
| [<span data-ttu-id="52886-124">System.Net.Connection.m\_WriteList Field</span><span class="sxs-lookup"><span data-stu-id="52886-124">System.Net.Connection.m\_WriteList Field</span></span>](m_writelist.md) |
| [<span data-ttu-id="52886-125">시스템 .Net ConnectionGroup 클래스</span><span class="sxs-lookup"><span data-stu-id="52886-125">System.Net.ConnectionGroup Class</span></span>](connectiongroup.md) |
| [<span data-ttu-id="52886-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span><span class="sxs-lookup"><span data-stu-id="52886-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](m_connectionlist.md) |
| [<span data-ttu-id="52886-127">CoreResponseData 클래스</span><span class="sxs-lookup"><span data-stu-id="52886-127">System.Net.CoreResponseData Class</span></span>](coreresponsedata.md) |
| [<span data-ttu-id="52886-128">System.Net.CoreResponseData.m\_ResponseHeaders Field</span><span class="sxs-lookup"><span data-stu-id="52886-128">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](coreresponsedata_m_responseheaders.md) |
| [<span data-ttu-id="52886-129">System.Net.CoreResponseData.m\_StatusCode Field</span><span class="sxs-lookup"><span data-stu-id="52886-129">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](coreresponsedata_m_statuscode.md) |
| [<span data-ttu-id="52886-130">시스템 .Net HttpWebRequest. \_AutoRedirects 필드</span><span class="sxs-lookup"><span data-stu-id="52886-130">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](_autoredirects.md) |
| [<span data-ttu-id="52886-131">시스템 .Net HttpWebRequest. \_CoreResponse 필드</span><span class="sxs-lookup"><span data-stu-id="52886-131">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](httpwebrequest__coreresponse.md) |
| [<span data-ttu-id="52886-132">시스템 .Net HttpWebRequest. \_Httpresponse.cache 필드</span><span class="sxs-lookup"><span data-stu-id="52886-132">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](_httpresponse.md) |
| [<span data-ttu-id="52886-133">System.Net.ServicePoint.m\_ConnectionGroupList Field</span><span class="sxs-lookup"><span data-stu-id="52886-133">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](m_connectiongrouplist.md) |
| [<span data-ttu-id="52886-134">System.Net.ServicePointManager.s\_ServicePointTable Field</span><span class="sxs-lookup"><span data-stu-id="52886-134">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](s_servicepointtable.md) |
| [<span data-ttu-id="52886-135">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span><span class="sxs-lookup"><span data-stu-id="52886-135">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [<span data-ttu-id="52886-136">DataMemberFieldEditor 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="52886-136">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](datamemberfieldeditor-class.md) |
| [<span data-ttu-id="52886-137">DataMemberListEditor 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="52886-137">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](datamemberlisteditor-class.md) |
  
## <a name="see-also"></a><span data-ttu-id="52886-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="52886-138">See also</span></span>

- [<span data-ttu-id="52886-139">.NET Framework 및 번외 릴리스</span><span class="sxs-lookup"><span data-stu-id="52886-139">The .NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
