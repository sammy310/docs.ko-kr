---
title: 부분적으로 신뢰할 수 있는 코드에서 라이브러리 사용
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], partially trusted code
- partially trusted code
- partial trust
- AllowPartiallyTrustedCallersAttribute attribute
- code access security, partially trusted code
- APTCA
ms.assetid: dd66cd4c-b087-415f-9c3e-94e3a1835f74
ms.openlocfilehash: 61291a07639c3f92a05f78dff49f6b20f1aee77e
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645715"
---
# <a name="using-libraries-from-partially-trusted-code"></a><span data-ttu-id="a29b2-102">부분적으로 신뢰할 수 있는 코드에서 라이브러리 사용</span><span class="sxs-lookup"><span data-stu-id="a29b2-102">Using Libraries from Partially Trusted Code</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
> [!NOTE]
> <span data-ttu-id="a29b2-103">이 항목에서는 강력한 이름의 어셈블리의 동작을 다루며 [수준 1](security-transparent-code-level-1.md) 어셈블리에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a29b2-103">This topic addresses the behavior of strong-named assemblies and applies only to [Level 1](security-transparent-code-level-1.md) assemblies.</span></span> <span data-ttu-id="a29b2-104">[.NET](security-transparent-code-level-2.md) Framework 4 이상에서 보안 투명 코드, 수준 2 어셈블리는 강력한 이름의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a29b2-104">[Security-Transparent Code, Level 2](security-transparent-code-level-2.md) assemblies in the .NET Framework 4 or later are not affected by strong names.</span></span> <span data-ttu-id="a29b2-105">보안 시스템의 변경 사항에 대한 자세한 내용은 [보안 변경](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a29b2-105">For more information about changes to the security system, see [Security Changes](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).</span></span>  
  
 <span data-ttu-id="a29b2-106">해당 호스트 또는 샌드박스로부터 완전 신뢰 미만을 받는 애플리케이션은 라이브러리 작성자가 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 특성을 사용하여 특별히 허용하지 않는 한 관리되는 공유 라이브러리를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a29b2-106">Applications that receive less than full trust from their host or sandbox are not allowed to call shared managed libraries unless the library writer specifically allows them to through the use of the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute.</span></span> <span data-ttu-id="a29b2-107">따라서 애플리케이션 작성자는 부분적으로 신뢰할 수 있는 컨텍스트에서 일부 라이브러리가 제공되지 않음을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a29b2-107">Therefore, application writers must be aware that some libraries will not be available to them from a partially trusted context.</span></span> <span data-ttu-id="a29b2-108">기본적으로 부분 신뢰 [샌드박스에서](how-to-run-partially-trusted-code-in-a-sandbox.md) 실행되고 완전 신뢰 어셈블리 목록에 없는 모든 코드는 부분적으로 신뢰할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a29b2-108">By default, all code that executes in a partial-trust [sandbox](how-to-run-partially-trusted-code-in-a-sandbox.md) and is not in the list of full-trust assemblies is partially trusted.</span></span> <span data-ttu-id="a29b2-109">코드가 부분적으로 신뢰할 수 있는 컨텍스트에서 실행되거나 부분적으로 신뢰할 수 있는 코드에서 호출되지 않는 경우에는 이 섹션의 내용에 주의할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a29b2-109">If you do not expect your code to be executed from a partially trusted context or to be called by partially trusted code, you do not have to be concerned about the information in this section.</span></span> <span data-ttu-id="a29b2-110">그러나 부분적으로 신뢰할 수 있는 코드와 상호 작용하거나 부분적으로 신뢰할 수 있는 컨텍스트에서 작동해야 하는 코드를 작성하는 경우 다음과 같은 요소를 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a29b2-110">However, if you write code that must interact with partially trusted code or operate from a partially trusted context, you should consider the following factors:</span></span>  
  
- <span data-ttu-id="a29b2-111">여러 애플리케이션에서 공유하려면 강력한 이름으로 라이브러리에 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a29b2-111">Libraries must be signed with a strong name in order to be shared by multiple applications.</span></span> <span data-ttu-id="a29b2-112">강력한 이름을 사용하면 코드를 전역 어셈블리 캐시에 배치하거나 샌드박싱 <xref:System.AppDomain>의 완전 신뢰 목록에 추가할 수 있으며, 소비자가 모바일 코드의 특정 부분이 실제로 사용자가 제공한 것인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a29b2-112">Strong names allow your code to be placed in the global assembly cache or added to the full-trust list of a sandboxing <xref:System.AppDomain>, and allow consumers to verify that a particular piece of mobile code actually originates from you.</span></span>  
  
- <span data-ttu-id="a29b2-113">기본적으로 강력한 이름의 [수준 1](security-transparent-code-level-1.md) 공유 라이브러리는 라이브러리 작성자가 아무 작업도 수행하지 않고도 완전 신뢰에 대한 암시적 [LinkDemand를](link-demands.md) 자동으로 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a29b2-113">By default, strong-named [Level 1](security-transparent-code-level-1.md) shared libraries perform an implicit [LinkDemand](link-demands.md) for full trust automatically, without the library writer having to do anything.</span></span>  
  
- <span data-ttu-id="a29b2-114">호출자에게 완전 신뢰가 없는데 이러한 라이브러리를 호출하려고 하면 런타임에서 <xref:System.Security.SecurityException>이 발생하고 호출자가 라이브러리에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a29b2-114">If a caller does not have full trust but still tries to call such a library, the runtime throws a <xref:System.Security.SecurityException> and the caller is not allowed to link to the library.</span></span>  
  
- <span data-ttu-id="a29b2-115">자동 **LinkDemand를** 사용하지 않도록 설정하고 예외가 throw되지 않도록 하려면 **허용PartiallyTrustedCallersAttribute** 특성을 공유 라이브러리의 어셈블리 범위에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a29b2-115">In order to disable the automatic **LinkDemand** and prevent the exception from being thrown, you can place the **AllowPartiallyTrustedCallersAttribute** attribute on the assembly scope of a shared library.</span></span> <span data-ttu-id="a29b2-116">이 특성을 사용하면 부분적으로 신뢰할 수 있는 관리 코드에서 라이브러리를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a29b2-116">This attribute allows your libraries to be called from partially trusted managed code.</span></span>  
  
- <span data-ttu-id="a29b2-117">이 특성을 사용하여 라이브러리 액세스 권한이 부여된, 부분적으로 신뢰할 수 있는 코드에는 여전히 <xref:System.AppDomain>에서 정의된 추가 제한 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a29b2-117">Partially trusted code that is granted access to a library with this attribute is still subject to further restrictions defined by the <xref:System.AppDomain>.</span></span>  
  
- <span data-ttu-id="a29b2-118">부분적으로 신뢰할 수 있는 코드가 **AllowPartiallyTrustedCallersAttribute** 특성이 없는 라이브러리를 호출하는 프로그래밍 방식은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a29b2-118">There is no programmatic way for partially trusted code to call a library that does not have the **AllowPartiallyTrustedCallersAttribute** attribute.</span></span>  
  
 <span data-ttu-id="a29b2-119">특정 응용 프로그램에 전용 라이브러리는 강력한 이름이나 **AllowPartiallyTrustedCallersAttribute** 특성이 필요하지 않으며 응용 프로그램 외부의 악의적인 코드에서 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a29b2-119">Libraries that are private to a specific application do not require a strong name or the **AllowPartiallyTrustedCallersAttribute** attribute and cannot be referenced by potentially malicious code outside the application.</span></span> <span data-ttu-id="a29b2-120">이러한 코드는 개발자가 특별한 작업을 수행하지 않아도 부분적으로 신뢰할 수 있는 모바일 코드에서 의도적이나 실수로 악용할 수 없도록 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="a29b2-120">Such code is protected against intentional or unintentional misuse by partially trusted mobile code without the developer having to do anything extra.</span></span>  
  
 <span data-ttu-id="a29b2-121">다음 형식의 코드에 대해서는 부분적으로 신뢰할 수 있는 코드가 사용할 수 있도록 명시적으로 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a29b2-121">You should consider explicitly enabling use by partially trusted code for the following types of code:</span></span>  
  
- <span data-ttu-id="a29b2-122">보안 취약점에 대해 부지런히 테스트되었으며 [보안 코딩 지침에](../../standard/security/secure-coding-guidelines.md)설명된 지침을 준수하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a29b2-122">Code that has been diligently tested for security vulnerabilities and is in compliance with the guidelines described in [Secure Coding Guidelines](../../standard/security/secure-coding-guidelines.md).</span></span>  
  
- <span data-ttu-id="a29b2-123">부분적으로 신뢰할 수 있는 시나리오를 위해 특별히 작성된 강력한 이름의 코드 라이브러리</span><span class="sxs-lookup"><span data-stu-id="a29b2-123">Strong-named code libraries that are specifically written for partially trusted scenarios.</span></span>  
  
- <span data-ttu-id="a29b2-124">인터넷에서 다운로드된 코드에서 호출하는 강력한 이름으로 서명된 모든 구성 요소(부분적으로 또는 완전히 신뢰할 수 있는지에 관계없음)</span><span class="sxs-lookup"><span data-stu-id="a29b2-124">Any components (whether partially or fully trusted) signed with a strong name that will be called by code that is downloaded from the Internet.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a29b2-125">.NET Framework 클래스 라이브러리의 일부 클래스에는 **AllowPartiallyTrustedCallersAttribute** 특성이 없으며 부분적으로 신뢰할 수 있는 코드에서 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a29b2-125">Some classes in the .NET Framework class library do not have the **AllowPartiallyTrustedCallersAttribute** attribute and cannot be called by partially trusted code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a29b2-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a29b2-126">See also</span></span>

- [<span data-ttu-id="a29b2-127">코드 액세스 보안</span><span class="sxs-lookup"><span data-stu-id="a29b2-127">Code Access Security</span></span>](code-access-security.md)
