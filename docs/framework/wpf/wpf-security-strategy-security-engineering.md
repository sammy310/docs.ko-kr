---
title: WPF 보안 전략 - 보안 엔지니어링
ms.date: 03/30/2017
helpviewer_keywords:
- security [WPF], testing techniques
- Security Development Lifecycle (SDL), security analysis [WPF]
- Security Development Lifecycle (SDL), threat modeling
- Security Development Lifecycle (SDL), testing techniques
- Security Development Lifecycle (SDL), source analysis tools
- Security Development Lifecycle (SDL), critical code management
- threat modeling [WPF]
ms.assetid: 0fc04394-4e47-49ca-b0cf-8cd1161d95b9
ms.openlocfilehash: c28fc87a71a1262ed5b3a6a04f615efc58e685ab
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2019
ms.locfileid: "67663339"
---
# <a name="wpf-security-strategy---security-engineering"></a><span data-ttu-id="5ca65-102">WPF 보안 전략 - 보안 엔지니어링</span><span class="sxs-lookup"><span data-stu-id="5ca65-102">WPF Security Strategy - Security Engineering</span></span>
<span data-ttu-id="5ca65-103">신뢰할 수 있는 컴퓨팅은 보안 코드 생성을 보장하기 위한 Microsoft 이니셔티브입니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-103">Trustworthy Computing is a Microsoft initiative for ensuring the production of secure code.</span></span> <span data-ttu-id="5ca65-104">신뢰할 수 있는 컴퓨팅 이니셔티브의 핵심 요소는 [!INCLUDE[TLA#tla_sdl](../../../includes/tlasharptla-sdl-md.md)]입니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-104">A key element of the Trustworthy Computing initiative is the [!INCLUDE[TLA#tla_sdl](../../../includes/tlasharptla-sdl-md.md)].</span></span> <span data-ttu-id="5ca65-105">[!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)]은 보안 코드 전달이 용이하도록 표준 엔지니어링 프로세스와 함께 사용되는 엔지니어링 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-105">The [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] is an engineering practice that is used in conjunction with standard engineering processes to facilitate the delivery of secure code.</span></span> <span data-ttu-id="5ca65-106">[!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)]은 형식화, 측정 가능성 및 다음을 비롯한 추가 구조와 모범 사례를 결합하는 10단계로 이루어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-106">The [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] consists of ten phases that combine best practices with formalization, measurability, and additional structure, including:</span></span>  
  
- <span data-ttu-id="5ca65-107">보안 디자인 분석</span><span class="sxs-lookup"><span data-stu-id="5ca65-107">Security design analysis</span></span>  
  
- <span data-ttu-id="5ca65-108">도구 기반 품질 검사</span><span class="sxs-lookup"><span data-stu-id="5ca65-108">Tool-based quality checks</span></span>  
  
- <span data-ttu-id="5ca65-109">침투 테스트</span><span class="sxs-lookup"><span data-stu-id="5ca65-109">Penetration testing</span></span>  
  
- <span data-ttu-id="5ca65-110">최종 보안 검토</span><span class="sxs-lookup"><span data-stu-id="5ca65-110">Final security review</span></span>  
  
- <span data-ttu-id="5ca65-111">릴리스 후 제품 보안 관리</span><span class="sxs-lookup"><span data-stu-id="5ca65-111">Post release product security management</span></span>  
  
## <a name="wpf-specifics"></a><span data-ttu-id="5ca65-112">WPF 고유 정보</span><span class="sxs-lookup"><span data-stu-id="5ca65-112">WPF Specifics</span></span>  
 <span data-ttu-id="5ca65-113">[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 엔지니어링 팀은 다음과 같은 주요 측면을 포함하는 [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)]을 적용하고 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-113">The [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] engineering team both applies and extends the [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)], the combination of which includes the following key aspects:</span></span>  
  
 [<span data-ttu-id="5ca65-114">위협 모델링</span><span class="sxs-lookup"><span data-stu-id="5ca65-114">Threat Modeling</span></span>](#threat_modeling)  
  
 [<span data-ttu-id="5ca65-115">보안 분석 및 편집 도구</span><span class="sxs-lookup"><span data-stu-id="5ca65-115">Security Analysis and Editing Tools</span></span>](#tools)  
  
 [<span data-ttu-id="5ca65-116">테스트 기술</span><span class="sxs-lookup"><span data-stu-id="5ca65-116">Testing Techniques</span></span>](#techniques)  
  
 [<span data-ttu-id="5ca65-117">중요한 코드 관리</span><span class="sxs-lookup"><span data-stu-id="5ca65-117">Critical Code Management</span></span>](#critical_code)  
  
<a name="threat_modeling"></a>   
### <a name="threat-modeling"></a><span data-ttu-id="5ca65-118">위협 모델링</span><span class="sxs-lookup"><span data-stu-id="5ca65-118">Threat Modeling</span></span>  
 <span data-ttu-id="5ca65-119">위협 모델링은 [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)]의 핵심 구성 요소이며, 잠재적인 보안 취약성을 확인하기 위해 시스템을 프로파일링하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-119">Threat modeling is a core component of the [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)], and is used to profile a system to determine potential security vulnerabilities.</span></span> <span data-ttu-id="5ca65-120">취약상이 식별되면 위협 모델링은 적절한 완화가 적용되었는지도 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-120">Once the vulnerabilities are identified, threat modeling also ensures that appropriate mitigations are in place.</span></span>  
  
 <span data-ttu-id="5ca65-121">높은 수준에서 위협 모델링은 식품점을 예로 들어 다음과 같은 주요 단계를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-121">At a high level, threat modeling involves the following key steps by using a grocery store as an example:</span></span>  
  
1. <span data-ttu-id="5ca65-122">**자산 식별**</span><span class="sxs-lookup"><span data-stu-id="5ca65-122">**Identifying Assets**.</span></span> <span data-ttu-id="5ca65-123">식품점의 자산에는 직원, 금고, 현금 등록기 및 재고가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-123">A grocery store's assets might include employees, a safe, cash registers, and inventory.</span></span>  
  
2. <span data-ttu-id="5ca65-124">**진입점 열거**</span><span class="sxs-lookup"><span data-stu-id="5ca65-124">**Enumerating Entry Points**.</span></span> <span data-ttu-id="5ca65-125">식품점의 진입점에는 앞문과 뒷문, 창, 하역장 및 에어컨 장치가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-125">A grocery store's entry points might include the front and back doors, windows, the loading dock, and air conditioning units.</span></span>  
  
3. <span data-ttu-id="5ca65-126">**진입점을 통한 자산 공격 조사**</span><span class="sxs-lookup"><span data-stu-id="5ca65-126">**Investigating Attacks against Assets using Entry Points**.</span></span> <span data-ttu-id="5ca65-127">한 가지 가능한 공격은 *에어컨* 진입점을 통해 식품점의 *금고* 자산을 대상으로 할 수 있습니다. 에어컨 장치의 나사를 풀어 금고를 상점 외부로 끌고 나갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-127">One possible attack could target a grocery store's *safe* asset through the *air conditioning* entry point; the air conditioning unit could be unscrewed to allow the safe to be pulled up through it and out of the store.</span></span>  
  
 <span data-ttu-id="5ca65-128">위협 모델링은 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 전체에 적용되며 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-128">Threat modeling is applied throughout [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] and includes the following:</span></span>  
  
- <span data-ttu-id="5ca65-129">[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 파서가 파일을 읽고, 텍스트를 해당 개체 모델 클래스에 매핑하고, 실제 코드를 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="5ca65-129">How the [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] parser reads files, maps text to corresponding object model classes, and creates the actual code.</span></span>  
  
- <span data-ttu-id="5ca65-130">창 핸들(hWnd)이 만들어지고, 메시지를 보내고, 창의 내용을 렌더링하는 데 사용되는 방법</span><span class="sxs-lookup"><span data-stu-id="5ca65-130">How a window handle (hWnd) is created, sends messages, and is used for rendering the contents of a window.</span></span>  
  
- <span data-ttu-id="5ca65-131">데이터 바인딩이 리소스를 가져오고 시스템과 상호 작용하는 방법</span><span class="sxs-lookup"><span data-stu-id="5ca65-131">How data binding obtains resources and interacts with the system.</span></span>  
  
 <span data-ttu-id="5ca65-132">이러한 위협 모델은 개발 프로세스 중 보안 디자인 요구 사항과 위협 완화를 식별하는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-132">These threat models are important for identifying security design requirements and threat mitigations during the development process.</span></span>  
  
<a name="tools"></a>   
### <a name="source-analysis-and-editing-tools"></a><span data-ttu-id="5ca65-133">소스 분석 및 편집 도구</span><span class="sxs-lookup"><span data-stu-id="5ca65-133">Source Analysis and Editing Tools</span></span>  
 <span data-ttu-id="5ca65-134">[!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)]의 수동 보안 코드 검토 요소 외에도 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 팀은 소스 분석 및 관련된 편집 작업에 여러 가지 도구를 사용하여 보안 취약성을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-134">In addition to the manual security code review elements of the [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)], the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] team uses several tools for source analysis and associated edits to decrease security vulnerabilities.</span></span> <span data-ttu-id="5ca65-135">다음을 포함하여 다양한 소스 도구가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-135">A wide range of source tools are used, and include the following:</span></span>  
  
- <span data-ttu-id="5ca65-136">**FXCop**: 상속 규칙에서 코드 액세스 보안 사용 및 비관리 코드와 안전 하 게 상호 운용 하는 방법에 이르기까지 관리 코드에서 일반적인 보안 문제를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-136">**FXCop**: Finds common security issues in managed code ranging from inheritance rules to code access security usage to how to safely interoperate with unmanaged code.</span></span> <span data-ttu-id="5ca65-137">[FXCop](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/bb429476%28v=vs.80%29)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5ca65-137">See [FXCop](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/bb429476%28v=vs.80%29).</span></span>  
  
- <span data-ttu-id="5ca65-138">**Prefix/Prefast**: 버퍼 오버런, 형식 문자열 문제 및 오류 검사 같은 비관리 코드에서 보안 취약성 및 일반적인 보안 문제를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-138">**Prefix/Prefast**: Finds security vulnerabilities and common security issues in unmanaged code such as buffer overruns, format string issues, and error checking.</span></span>  
  
- <span data-ttu-id="5ca65-139">**금지 된 Api**: 소스는 같은 보안 문제가 발생 하는 것에 대 한 잘 알려진 함수가 실수로 사용을 식별 하는 코드 검색 `strcpy`합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-139">**Banned APIs**: Searches source code to identify accidental usage of functions that are well-known for causing security issues, such as `strcpy`.</span></span> <span data-ttu-id="5ca65-140">식별 되 면 이러한 함수는 보다 안전한 대체 항목으로 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-140">Once identified, these functions are replaced with alternatives that are more secure.</span></span>  
  
<a name="techniques"></a>   
### <a name="testing-techniques"></a><span data-ttu-id="5ca65-141">테스트 기술</span><span class="sxs-lookup"><span data-stu-id="5ca65-141">Testing Techniques</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="5ca65-142">는 다음을 포함하는 다양한 보안 테스트 기술을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-142">uses a variety of security testing techniques that include:</span></span>  
  
- <span data-ttu-id="5ca65-143">**Whitebox 테스트**: 테스터가 소스 코드를 한 다음 악용 테스트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-143">**Whitebox Testing**: Testers view source code, and then build exploit tests.</span></span>
  
- <span data-ttu-id="5ca65-144">**Blackbox 테스트**: 테스터가 API 및 기능을 검사 하 여 보안 익를 찾으려고 시도 및 제품을 공격 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-144">**Blackbox Testing**: Testers try to find security exploits by examining the API and features, and then try to attack the product.</span></span>  
  
- <span data-ttu-id="5ca65-145">**다른 제품의 문제 재발 보안**: 경우에 관련된 제품의 보안 문제가 테스트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-145">**Regressing Security Issues from other Products**: Where relevant, security issues from related products are tested.</span></span> <span data-ttu-id="5ca65-146">예를 들어 [!INCLUDE[TLA2#tla_ie](../../../includes/tla2sharptla-ie-md.md)]과 관련된 약 60여 개 보안 문제의 적절한 변형이 식별되고 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]에 적용할 수 있는지 시도되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-146">For example, appropriate variants of approximately sixty security issues for [!INCLUDE[TLA2#tla_ie](../../../includes/tla2sharptla-ie-md.md)] have been identified and tried for their applicability to [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)].</span></span>  
  
- <span data-ttu-id="5ca65-147">**파일 퍼지 테스트를 통해 도구 기반 침투 테스트**: 파일 퍼지 테스트는 파일 판독기의 악용의 다양 한 입력을 통해 범위를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-147">**Tools-Based Penetration Testing through File Fuzzing**: File fuzzing is the exploitation of a file reader's input range through a variety of inputs.</span></span> <span data-ttu-id="5ca65-148">[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]에서 이 기술이 사용되는 한 가지 예는 이미지 디코딩 코드 오류 검사입니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-148">One example in [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] where this technique is used is to check for failure in image decoding code.</span></span>  
  
<a name="critical_code"></a>   
### <a name="critical-code-management"></a><span data-ttu-id="5ca65-149">중요한 코드 관리</span><span class="sxs-lookup"><span data-stu-id="5ca65-149">Critical Code Management</span></span>  
 <span data-ttu-id="5ca65-150">에 대 한 [!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)]하십시오 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 표시 하 고 보안에 중요 한 권한을 높이 코드를 추적에 대 한.NET Framework 지원을 사용 하 여 보안 샌드박스를 빌드합니다 (참조 **보안에 중요 한 방법론** 에서 [WPF 보안 전략-플랫폼 보안](wpf-security-strategy-platform-security.md)).</span><span class="sxs-lookup"><span data-stu-id="5ca65-150">For [!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)], [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] builds a security sandbox by using .NET Framework support for marking and tracking security-critical code that elevates privileges (see **Security-Critical Methodology** in [WPF Security Strategy - Platform Security](wpf-security-strategy-platform-security.md)).</span></span> <span data-ttu-id="5ca65-151">보안에 중요한 코드의 높은 보안 품질 요구 사항을 감안하여 이러한 코드는 추가 수준의 소스 관리 제어 및 보안 감사를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-151">Given the high security quality requirements on security critical code, such code receives an additional level of source management control and security audit.</span></span> <span data-ttu-id="5ca65-152">[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]의 약 5%-10%는 전담 검토팀이 검토하는 보안에 중요한 코드로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-152">Approximately 5% to 10% of [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] consists of security-critical code, which is reviewed by a dedicated reviewing team.</span></span> <span data-ttu-id="5ca65-153">소스 코드 및 체크 인 프로세스는 보안에 중요한 코드를 추적하고 중요한 엔터티(예: 중요한 코드가 포함된 메서드)를 사인오프 상태로 매핑하여 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-153">The source code and check-in process is managed by tracking security critical code and mapping each critical entity (i.e. a method that contains critical code) to its sign off state.</span></span> <span data-ttu-id="5ca65-154">사인오프 상태에는 하나 이상의 검토자 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-154">The sign off state includes the names of one or more reviewers.</span></span> <span data-ttu-id="5ca65-155">[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]의 각 일별 빌드는 중요한 코드를 이전 빌드의 코드와 비교하여 승인되지 않은 변경 내용을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-155">Each daily build of [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] compares the critical code to that in previous builds to check for unapproved changes.</span></span> <span data-ttu-id="5ca65-156">엔지니어가 검토팀의 승인 없이 중요한 코드를 수정하는 경우 식별되어 즉시 수정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-156">If an engineer modifies critical code without approval from the reviewing team, it is identified and fixed immediately.</span></span> <span data-ttu-id="5ca65-157">이 프로세스를 통해 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 샌드박스 코드에 특히 높은 수준의 감시를 적용하고 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ca65-157">This process enables the application and maintenance of an especially high level of scrutiny over [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] sandbox code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ca65-158">참고자료</span><span class="sxs-lookup"><span data-stu-id="5ca65-158">See also</span></span>

- [<span data-ttu-id="5ca65-159">보안</span><span class="sxs-lookup"><span data-stu-id="5ca65-159">Security</span></span>](security-wpf.md)
- [<span data-ttu-id="5ca65-160">WPF 부분 신뢰 보안</span><span class="sxs-lookup"><span data-stu-id="5ca65-160">WPF Partial Trust Security</span></span>](wpf-partial-trust-security.md)
- [<span data-ttu-id="5ca65-161">WPF 보안 전략 - 플랫폼 보안</span><span class="sxs-lookup"><span data-stu-id="5ca65-161">WPF Security Strategy - Platform Security</span></span>](wpf-security-strategy-platform-security.md)
- [<span data-ttu-id="5ca65-162">신뢰할 수 있는 컴퓨팅</span><span class="sxs-lookup"><span data-stu-id="5ca65-162">Trustworthy Computing</span></span>](https://www.microsoft.com/mscorp/twc/default.mspx)
- [<span data-ttu-id="5ca65-163">.NET의 보안</span><span class="sxs-lookup"><span data-stu-id="5ca65-163">Security in .NET</span></span>](../../standard/security/index.md)
