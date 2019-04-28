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
---

# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="dc8d8-102">추가 클래스 라이브러리 및 API</span><span class="sxs-lookup"><span data-stu-id="dc8d8-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="dc8d8-103">.NET Framework는 지속적으로 발전 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8d8-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="dc8d8-104">플랫폼 간 개발을 개선 하 고 새로운 기능을 일찍 소개를 대역 외 (OOB)에서 새로운 기능이 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc8d8-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="dc8d8-105">이 항목에서는 설명서를 제공하는 OOB 프로젝트를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8d8-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="dc8d8-106">또한 일부 라이브러리는 .NET Framework의 구현이나 특정 플랫폼을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8d8-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="dc8d8-107">예를 들어를 <xref:System.Text.CodePagesEncodingProvider> 클래스는.NET Framework를 사용 하 여 개발 하는 UWP 앱에 사용할 수 있는 코드 페이지 인코딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dc8d8-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="dc8d8-108">이 항목에서는 이러한 라이브러리도 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc8d8-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="dc8d8-109">OOB 프로젝트</span><span class="sxs-lookup"><span data-stu-id="dc8d8-109">OOB projects</span></span>
  
| <span data-ttu-id="dc8d8-110">프로젝트</span><span class="sxs-lookup"><span data-stu-id="dc8d8-110">Project</span></span> | <span data-ttu-id="dc8d8-111">설명</span><span class="sxs-lookup"><span data-stu-id="dc8d8-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="dc8d8-112">해당 내용을 절대로 변경하지 않도록 보장하는 안전한 스레드인 컬렉션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8d8-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="dc8d8-113">Windows의 WinHTTP 인터페이스에 따라 <xref:System.Net.Http.HttpClient> 에 메시지 처리기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8d8-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="dc8d8-114">SIMD 하드웨어 기반 가속을 활용할 수 있는 벡터 형식 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="dc8d8-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="dc8d8-115">TPL 데이터 흐름 라이브러리는 동시성 사용 애플리케이션의 견고성을 높이는 데 도움이 되는 데이터 흐름 구성 요소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8d8-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="dc8d8-116">플랫폼별 라이브러리</span><span class="sxs-lookup"><span data-stu-id="dc8d8-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="dc8d8-117">프로젝트</span><span class="sxs-lookup"><span data-stu-id="dc8d8-117">Project</span></span> | <span data-ttu-id="dc8d8-118">설명</span><span class="sxs-lookup"><span data-stu-id="dc8d8-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="dc8d8-119">확장 된 <xref:System.Text.EncodingProvider> 클래스 코드 페이지 인코딩을 유니버설 Windows 플랫폼을 대상으로 하는 앱에 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8d8-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="dc8d8-120">전용 API</span><span class="sxs-lookup"><span data-stu-id="dc8d8-120">Private APIs</span></span>  

<span data-ttu-id="dc8d8-121">이러한 API는 제품 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc8d8-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="dc8d8-122">API 이름</span><span class="sxs-lookup"><span data-stu-id="dc8d8-122">API Name</span></span> |
| -------- |
| [<span data-ttu-id="dc8d8-123">System.Net.Connection 클래스</span><span class="sxs-lookup"><span data-stu-id="dc8d8-123">System.Net.Connection Class</span></span>](../../../docs/framework/additional-apis/connection.md) |
| [<span data-ttu-id="dc8d8-124">System.Net.Connection.m\_WriteList Field</span><span class="sxs-lookup"><span data-stu-id="dc8d8-124">System.Net.Connection.m\_WriteList Field</span></span>](../../../docs/framework/additional-apis/m_writelist.md) |
| [<span data-ttu-id="dc8d8-125">System.Net.ConnectionGroup 클래스</span><span class="sxs-lookup"><span data-stu-id="dc8d8-125">System.Net.ConnectionGroup Class</span></span>](../../../docs/framework/additional-apis/connectiongroup.md) |
| [<span data-ttu-id="dc8d8-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span><span class="sxs-lookup"><span data-stu-id="dc8d8-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](../../../docs/framework/additional-apis/m_connectionlist.md) |
| [<span data-ttu-id="dc8d8-127">System.Net.CoreResponseData 클래스</span><span class="sxs-lookup"><span data-stu-id="dc8d8-127">System.Net.CoreResponseData Class</span></span>](../../../docs/framework/additional-apis/coreresponsedata.md) |
| [<span data-ttu-id="dc8d8-128">System.Net.CoreResponseData.m\_ResponseHeaders Field</span><span class="sxs-lookup"><span data-stu-id="dc8d8-128">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](../../../docs/framework/additional-apis/coreresponsedata_m_responseheaders.md) |
| [<span data-ttu-id="dc8d8-129">System.Net.CoreResponseData.m\_StatusCode Field</span><span class="sxs-lookup"><span data-stu-id="dc8d8-129">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](../../../docs/framework/additional-apis/coreresponsedata_m_statuscode.md) |
| [<span data-ttu-id="dc8d8-130">System.Net.HttpWebRequest 합니다. \_AutoRedirects 필드</span><span class="sxs-lookup"><span data-stu-id="dc8d8-130">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](../../../docs/framework/additional-apis/_autoredirects.md) |
| [<span data-ttu-id="dc8d8-131">System.Net.HttpWebRequest 합니다. \_CoreResponse 필드</span><span class="sxs-lookup"><span data-stu-id="dc8d8-131">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](../../../docs/framework/additional-apis/httpwebrequest__coreresponse.md) |
| [<span data-ttu-id="dc8d8-132">System.Net.HttpWebRequest 합니다. \_HttpResponse 필드</span><span class="sxs-lookup"><span data-stu-id="dc8d8-132">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](../../../docs/framework/additional-apis/_httpresponse.md) |
| [<span data-ttu-id="dc8d8-133">System.Net.ServicePoint.m\_ConnectionGroupList Field</span><span class="sxs-lookup"><span data-stu-id="dc8d8-133">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](../../../docs/framework/additional-apis/m_connectiongrouplist.md) |
| [<span data-ttu-id="dc8d8-134">System.Net.ServicePointManager.s\_ServicePointTable Field</span><span class="sxs-lookup"><span data-stu-id="dc8d8-134">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](../../../docs/framework/additional-apis/s_servicepointtable.md) |
| [<span data-ttu-id="dc8d8-135">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span><span class="sxs-lookup"><span data-stu-id="dc8d8-135">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [<span data-ttu-id="dc8d8-136">System.Windows.Forms.Design.DataMemberFieldEditor 클래스</span><span class="sxs-lookup"><span data-stu-id="dc8d8-136">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |
| [<span data-ttu-id="dc8d8-137">System.Windows.Forms.Design.DataMemberListEditor 클래스</span><span class="sxs-lookup"><span data-stu-id="dc8d8-137">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |
  
## <a name="see-also"></a><span data-ttu-id="dc8d8-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="dc8d8-138">See also</span></span>

- [<span data-ttu-id="dc8d8-139">.NET Framework 및 번외 릴리스</span><span class="sxs-lookup"><span data-stu-id="dc8d8-139">The .NET Framework and Out-of-Band Releases</span></span>](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)
