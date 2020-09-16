---
title: 코드 액세스 보안 기본 사항
description: CLR을 대상으로 하는 앱에 대 한 코드 액세스 보안 기본 사항에 대해 알아봅니다. 형식이 안전한 코드, 명령적 및 선언적 구문, 보안 클래스 라이브러리 및 투명 코드를 확인 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], code access security
ms.assetid: 4eaa6535-d9fe-41a1-91d8-b437cfc16921
ms.openlocfilehash: 9f6049913a2e8cf3e3f220b0148598a236b60bef
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557073"
---
# <a name="code-access-security-basics"></a><span data-ttu-id="d0399-103">코드 액세스 보안 기본 사항</span><span class="sxs-lookup"><span data-stu-id="d0399-103">Code Access Security Basics</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="d0399-104">공용 언어 런타임을 대상으로 하는 모든 애플리케이션(즉, 관리되는 모든 애플리케이션)은 런타임의 보안 시스템과 상호 작용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-104">Every application that targets the common language runtime (that is, every managed application) must interact with the runtime's security system.</span></span> <span data-ttu-id="d0399-105">관리되는 애플리케이션이 로드되면 해당 호스트가 자동으로 권한 집합을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-105">When a managed application is loaded, its host automatically grants it a set of permissions.</span></span> <span data-ttu-id="d0399-106">이러한 권한은 호스트의 로컬 보안 설정이나 애플리케이션이 있는 샌드박스에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-106">These permissions are determined by the host's local security settings or by the sandbox the application is in.</span></span> <span data-ttu-id="d0399-107">이러한 권한에 따라 애플리케이션이 올바르게 실행되거나 보안 예외를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-107">Depending on these permissions, the application either runs properly or generates a security exception.</span></span>

<span data-ttu-id="d0399-108">데스크톱 애플리케이션에 대한 기본 호스트는 완전 신뢰로 코드를 실행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-108">The default host for desktop applications allows code to run in full trust.</span></span> <span data-ttu-id="d0399-109">따라서 애플리케이션이 데스크톱을 대상으로 하는 경우 무제한 권한 집합을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-109">Therefore, if your application targets the desktop, it has an unrestricted permission set.</span></span> <span data-ttu-id="d0399-110">다른 호스트 또는 샌드박스는 애플리케이션에 대해 제한된 권한 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-110">Other hosts or sandboxes provide a limited permission set for applications.</span></span> <span data-ttu-id="d0399-111">호스트마다 권한 집합이 변경될 수 있으므로 대상 호스트에서 허용하는 권한만 사용하도록 애플리케이션을 디자인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-111">Because the permission set can change from host to host, you must design your application to use only the permissions that your target host allows.</span></span>

<span data-ttu-id="d0399-112">공용 언어 런타임을 대상으로 하는 효과적인 애플리케이션을 작성하려면 다음 코드 액세스 보안 개념을 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-112">You must be familiar with the following code access security concepts in order to write effective applications that target the common language runtime:</span></span>

- <span data-ttu-id="d0399-113">**형식 안전 코드**: 형식이 안전한 코드는 잘 정의 된 허용 되는 방식 으로만 형식에 액세스 하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-113">**Type-safe code**: Type-safe code is code that accesses types only in well-defined, allowable ways.</span></span> <span data-ttu-id="d0399-114">예를 들어 유효한 개체 참조가 지정된 경우 형식이 안전한 코드는 실제 필드 멤버에 해당하는 고정된 오프셋의 메모리에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-114">For example, given a valid object reference, type-safe code can access memory at fixed offsets that correspond to actual field members.</span></span> <span data-ttu-id="d0399-115">코드가 공개적으로 노출된 해당 개체의 필드에 속하는 메모리 범위를 벗어난 임의 오프셋의 메모리에 액세스하는 경우에는 형식이 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-115">If the code accesses memory at arbitrary offsets outside the range of memory that belongs to that object's publicly exposed fields, it is not type-safe.</span></span> <span data-ttu-id="d0399-116">코드가 코드 액세스 보안을 활용할 수 있게 하려면 형식 안정성이 확인된 코드를 생성하는 컴파일러를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-116">To enable code to benefit from code access security, you must use a compiler that generates verifiably type-safe code.</span></span> <span data-ttu-id="d0399-117">자세한 내용은이 항목의 뒷부분에 있는 [안정형 형식 안전 코드 작성](#typesafe_code) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d0399-117">For more information, see the [Writing Verifiably Type-Safe Code](#typesafe_code) section later in this topic.</span></span>

- <span data-ttu-id="d0399-118">**명령적 및 선언적 구문**: 공용 언어 런타임을 대상으로 하는 코드는 권한을 요청 하 고, 호출자에 게 권한을 지정 하 고, 특정 보안 설정 (충분 한 권한이 부여 됨)을 재정의 하 여 보안 시스템과 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-118">**Imperative and declarative syntax**: Code that targets the common language runtime can interact with the security system by requesting permissions, demanding that callers have specified permissions, and overriding certain security settings (given enough privileges).</span></span> <span data-ttu-id="d0399-119">선언적 구문 및 명령적 구문의 두 가지 구문 형식은 사용하여 .NET Framework 보안 시스템과 프로그래밍 방식으로 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-119">You use two forms of syntax to programmatically interact with the .NET Framework security system: declarative syntax and imperative syntax.</span></span> <span data-ttu-id="d0399-120">선언적 호출은 특성을 사용하여 수행되고, 명령적 호출은 코드 내에서 클래스의 새 인스턴스를 사용하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-120">Declarative calls are performed using attributes; imperative calls are performed using new instances of classes within your code.</span></span> <span data-ttu-id="d0399-121">명령적으로만 수행할 수 있는 호출도 있고, 선언적으로만 수행할 수 있는 호출도 있고, 두 가지 방식 중 하나로 수행할 수 있는 호출도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-121">Some calls can be performed only imperatively, others can be performed only declaratively, and some calls can be performed in either manner.</span></span>

- <span data-ttu-id="d0399-122">보안 **클래스 라이브러리**: 보안 클래스 라이브러리는 보안 요구를 사용 하 여 라이브러리의 호출자가 라이브러리에서 노출 하는 리소스에 액세스할 수 있는 권한을 갖고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-122">**Secure class libraries**: A secure class library uses security demands to ensure that the library's callers have permission to access the resources that the library exposes.</span></span> <span data-ttu-id="d0399-123">예를 들어 보안 클래스 라이브러리에 호출자에게 파일을 만들 수 있는 권한이 있도록 요구하는 파일 생성 메서드가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-123">For example, a secure class library might have a method for creating files that would demand that its callers have permissions to create files.</span></span> <span data-ttu-id="d0399-124">.NET Framework는 보안 클래스 라이브러리로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-124">The .NET Framework consists of secure class libraries.</span></span> <span data-ttu-id="d0399-125">코드에서 사용하는 라이브러리에 액세스하는 데 필요한 권한을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-125">You should be aware of the permissions required to access any library that your code uses.</span></span> <span data-ttu-id="d0399-126">자세한 내용은이 항목의 뒷부분에 있는 [보안 클래스 라이브러리 사용](#secure_library) 단원을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d0399-126">For more information, see the [Using Secure Class Libraries](#secure_library) section later in this topic.</span></span>

- <span data-ttu-id="d0399-127">**투명 코드**: 특정 사용 권한을 식별 하는 것 외에도 .NET Framework 4부터 코드를 보안 투명으로 실행할지 여부도 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-127">**Transparent code**: Starting with the .NET Framework 4, in addition to identifying specific permissions, you must also determine whether your code should run as security-transparent.</span></span> <span data-ttu-id="d0399-128">보안 투명 코드는 보안에 중요한 것으로 식별된 형식이나 멤버를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-128">Security-transparent code cannot call types or members that are identified as security-critical.</span></span> <span data-ttu-id="d0399-129">이 규칙은 완전 신뢰 애플리케이션과 부분적으로 신뢰할 수 있는 애플리케이션에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-129">This rule applies to full-trust applications as well as partially trusted applications.</span></span> <span data-ttu-id="d0399-130">자세한 내용은 [보안 투명 코드](security-transparent-code.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d0399-130">For more information, see [Security-Transparent Code](security-transparent-code.md).</span></span>

<a name="typesafe_code"></a>

## <a name="writing-verifiably-type-safe-code"></a><span data-ttu-id="d0399-131">형식 안정성이 확인된 코드 작성</span><span class="sxs-lookup"><span data-stu-id="d0399-131">Writing Verifiably Type-Safe Code</span></span>

<span data-ttu-id="d0399-132">JIT(Just-In-Time) 컴파일은 코드를 검사하고 코드의 형식이 안전한지 여부를 확인하려고 하는 검증 프로세스를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-132">Just-in-time (JIT) compilation performs a verification process that examines code and tries to determine whether the code is type-safe.</span></span> <span data-ttu-id="d0399-133">확인 하는 동안 형식이 안전한 것으로 입증 된 코드를 *안정형 형식 안전 코드*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-133">Code that is proven during verification to be type-safe is called *verifiably type-safe code*.</span></span> <span data-ttu-id="d0399-134">코드 형식이 안전해도 검증 프로세스나 컴파일러의 제한 사항 때문에 형식 안전성이 아직 확인되지 않았을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-134">Code can be type-safe, yet might not be verifiably type-safe because of the limitations of the verification process or of the compiler.</span></span> <span data-ttu-id="d0399-135">모든 언어가 형식이 안전한 것은 아니며, Microsoft Visual C++와 같은 일부 언어 컴파일러는 형식 안전성이 확인된 관리 코드를 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-135">Not all languages are type-safe, and some language compilers, such as Microsoft Visual C++, cannot generate verifiably type-safe managed code.</span></span> <span data-ttu-id="d0399-136">사용하는 언어 컴파일러가 형식 안전성이 확인된 코드를 생성하는지 여부를 확인하려면 컴파일러의 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d0399-136">To determine whether the language compiler you use generates verifiably type-safe code, consult the compiler's documentation.</span></span> <span data-ttu-id="d0399-137">특정 언어 구문을 사용 하지 않는 경우에만 확인 가능한 형식 안전 코드를 생성 하는 언어 컴파일러를 사용 하는 경우 [PEVerify 도구](../tools/peverify-exe-peverify-tool.md) 를 사용 하 여 코드의 형식이 안전한 지 여부를 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-137">If you use a language compiler that generates verifiably type-safe code only when you avoid certain language constructs, you might want to use the [PEVerify tool](../tools/peverify-exe-peverify-tool.md) to determine whether your code is verifiably type-safe.</span></span>

<span data-ttu-id="d0399-138">보안 정책에서 검증을 건너뛸 수 있도록 허용하는 경우 형식 안전성이 확인되지 않은 코드가 실행을 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-138">Code that is not verifiably type-safe can attempt to execute if security policy allows the code to bypass verification.</span></span> <span data-ttu-id="d0399-139">그러나 형식 안전성은 런타임의 어셈블리 격리 메커니즘에서 필수 부분이므로 코드가 형식 안전성 규칙을 위반하는 경우 보안을 안정적으로 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-139">However, because type safety is an essential part of the runtime's mechanism for isolating assemblies, security cannot be reliably enforced if code violates the rules of type safety.</span></span> <span data-ttu-id="d0399-140">기본적으로 형식이 안전하지 않은 코드는 로컬 컴퓨터에서 시작된 경우에만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-140">By default, code that is not type-safe is allowed to run only if it originates from the local computer.</span></span> <span data-ttu-id="d0399-141">따라서 모바일 코드는 형식이 안전해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-141">Therefore, mobile code should be type-safe.</span></span>

<a name="secure_library"></a>

## <a name="using-secure-class-libraries"></a><span data-ttu-id="d0399-142">보안 클래스 라이브러리 사용</span><span class="sxs-lookup"><span data-stu-id="d0399-142">Using Secure Class Libraries</span></span>

<span data-ttu-id="d0399-143">코드가 클래스 라이브러리에 필요한 권한을 요청하고 부여된 경우 라이브러리에 액세스할 수 있으며, 라이브러리에서 노출하는 리소스가 무단 액세스로부터 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-143">If your code requests and is granted the permissions required by the class library, it will be allowed to access the library and the resources that the library exposes will be protected from unauthorized access.</span></span> <span data-ttu-id="d0399-144">코드에 적절한 권한이 없는 경우 클래스 라이브러리에 액세스할 수 없으며, 악성 코드가 코드를 사용하여 보호된 리소스에 간접적으로 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-144">If your code does not have the appropriate permissions, it will not be allowed to access the class library, and malicious code will not be able to use your code to indirectly access protected resources.</span></span> <span data-ttu-id="d0399-145">코드를 호출하는 다른 코드에도 라이브러리에 액세스할 수 있는 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-145">Other code that calls your code must also have permission to access the library.</span></span> <span data-ttu-id="d0399-146">권한이 없는 경우 코드 실행도 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-146">If it does not, your code will be restricted from running as well.</span></span>

<span data-ttu-id="d0399-147">코드 액세스 보안은 코드를 작성하는 사람의 오류 가능성을 제거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-147">Code access security does not eliminate the possibility of human error in writing code.</span></span> <span data-ttu-id="d0399-148">그러나 애플리케이션이 보안 클래스 라이브러리를 사용하여 보호된 리소스에 액세스하는 경우 클래스 라이브러리에서 잠재적인 보안 문제가 철저히 검사되기 때문에 애플리케이션 코드의 보안 위험이 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-148">However, if your application uses secure class libraries to access protected resources, the security risk for application code is decreased, because class libraries are closely scrutinized for potential security problems.</span></span>

## <a name="declarative-security"></a><span data-ttu-id="d0399-149">선언적 보안</span><span class="sxs-lookup"><span data-stu-id="d0399-149">Declarative Security</span></span>

<span data-ttu-id="d0399-150">선언적 보안 구문에서는 [특성](../../standard/attributes/index.md) 을 사용 하 여 보안 정보를 코드의 [메타 데이터로](../../standard/metadata-and-self-describing-components.md) 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-150">Declarative security syntax uses [attributes](../../standard/attributes/index.md) to place security information into the [metadata](../../standard/metadata-and-self-describing-components.md) of your code.</span></span> <span data-ttu-id="d0399-151">어셈블리, 클래스 또는 멤버 수준에 특성을 배치하여 사용할 요청, 요구 또는 재정의 형식을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-151">Attributes can be placed at the assembly, class, or member level, to indicate the type of request, demand, or override you want to use.</span></span> <span data-ttu-id="d0399-152">요청은 애플리케이션이 요구하거나 원하지 않는 권한에 대해 런타임 보안 시스템에 알리기 위해 공용 언어 런타임을 대상으로 하는 애플리케이션에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-152">Requests are used in applications that target the common language runtime to inform the runtime security system about the permissions that your application needs or does not want.</span></span> <span data-ttu-id="d0399-153">요구와 재정의는 호출자로부터 리소스를 보호하거나 기본 보안 동작을 재정의하기 위해 라이브러리에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-153">Demands and overrides are used in libraries to help protect resources from callers or to override default security behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="d0399-154">.NET Framework 4에서는 .NET Framework 보안 모델 및 용어에 대 한 중요 한 변경 내용이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-154">In the .NET Framework 4, there have been important changes to the .NET Framework security model and terminology.</span></span> <span data-ttu-id="d0399-155">이러한 변경 내용에 대 한 자세한 내용은 [보안 변경 내용](/previous-versions/dotnet/framework/security/security-changes)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d0399-155">For more information about these changes, see [Security Changes](/previous-versions/dotnet/framework/security/security-changes).</span></span>

<span data-ttu-id="d0399-156">선언적 보안 호출을 사용하려면 필요한 특정 형식의 권한을 나타내도록 권한 개체의 상태 데이터를 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-156">In order to use declarative security calls, you must initialize the state data of the permission object so that it represents the particular form of permission you need.</span></span> <span data-ttu-id="d0399-157">모든 기본 제공 권한에는 수행할 보안 작업 형식을 설명하는 <xref:System.Security.Permissions.SecurityAction> 열거형이 전달되는 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-157">Every built-in permission has an attribute that is passed a <xref:System.Security.Permissions.SecurityAction> enumeration to describe the type of security operation you want to perform.</span></span> <span data-ttu-id="d0399-158">그러나 권한은 고유한 전용 매개 변수도 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-158">However, permissions also accept their own parameters that are exclusive to them.</span></span>

<span data-ttu-id="d0399-159">다음 코드 조각에서는 코드의 호출자에게 `MyPermission`이라는 사용자 지정 권한이 있도록 요청하는 선언적 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-159">The following code fragment shows declarative syntax for requesting that your code's callers have a custom permission called `MyPermission`.</span></span> <span data-ttu-id="d0399-160">이 권한은 가상의 사용자 지정 권한이며 .NET Framework에 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-160">This permission is a hypothetical custom permission and does not exist in the .NET Framework.</span></span> <span data-ttu-id="d0399-161">이 예제에서 선언적 호출은 클래스 정의 바로 앞에 배치되며 이 권한이 클래스 수준에 적용되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-161">In this example, the declarative call is placed directly before the class definition, specifying that this permission be applied to the class level.</span></span> <span data-ttu-id="d0399-162">이 특성에는 호출자가를 실행 하기 위해이 권한이 있어야 하도록 지정 하기 위해 **SecurityAction** 구조가 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-162">The attribute is passed a **SecurityAction.Demand** structure to specify that callers must have this permission in order to run.</span></span>

```vb
<MyPermission(SecurityAction.Demand, Unrestricted = True)> Public Class MyClass1

   Public Sub New()
      'The constructor is protected by the security call.
   End Sub

   Public Sub MyMethod()
      'This method is protected by the security call.
   End Sub

   Public Sub YourMethod()
      'This method is protected by the security call.
   End Sub
End Class
```

```csharp
[MyPermission(SecurityAction.Demand, Unrestricted = true)]
public class MyClass
{
   public MyClass()
   {
      //The constructor is protected by the security call.
   }

   public void MyMethod()
   {
      //This method is protected by the security call.
   }

   public void YourMethod()
   {
      //This method is protected by the security call.
   }
}
```

## <a name="imperative-security"></a><span data-ttu-id="d0399-163">명령적 보안</span><span class="sxs-lookup"><span data-stu-id="d0399-163">Imperative Security</span></span>

<span data-ttu-id="d0399-164">명령적 보안 구문은 호출할 권한 개체의 새 인스턴스를 만들어 보안 호출을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-164">Imperative security syntax issues a security call by creating a new instance of the permission object you want to invoke.</span></span> <span data-ttu-id="d0399-165">명령적 구문을 사용하여 요구 및 재정의를 수행할 수 있지만 요청은 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-165">You can use imperative syntax to perform demands and overrides, but not requests.</span></span>

<span data-ttu-id="d0399-166">보안 호출을 수행하기 전에 필요한 특정 형식의 권한을 나타내도록 권한 개체의 상태 데이터를 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-166">Before you make the security call, you must initialize the state data of the permission object so that it represents the particular form of the permission you need.</span></span> <span data-ttu-id="d0399-167">예를 들어 개체를 만들 때 <xref:System.Security.Permissions.FileIOPermission> 생성자를 사용 하 여 모든 파일에 대 한 무제한 액세스 또는 파일에 대 한 액세스 권한 없음을 나타내도록 **FileIOPermission** 개체를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-167">For example, when creating a <xref:System.Security.Permissions.FileIOPermission> object, you can use the constructor to initialize the **FileIOPermission** object so that it represents either unrestricted access to all files or no access to files.</span></span> <span data-ttu-id="d0399-168">또는 다른 **FileIOPermission** 개체를 사용 하 여 개체에서 나타낼 액세스 형식 (즉, 읽기, 추가 또는 쓰기) 및 개체에서 보호할 파일을 나타내는 매개 변수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-168">Or, you can use a different **FileIOPermission** object, passing parameters that indicate the type of access you want the object to represent (that is, read, append, or write) and what files you want the object to protect.</span></span>

<span data-ttu-id="d0399-169">명령적 보안 구문을 사용하여 단일 보안 개체를 호출하는 것은 물론 권한 집합에 있는 권한 그룹을 초기화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-169">In addition to using imperative security syntax to invoke a single security object, you can use it to initialize a group of permissions in a permission set.</span></span> <span data-ttu-id="d0399-170">예를 들어이 기술은 한 방법으로 여러 권한에 대해 [assert](using-the-assert-method.md) 호출을 안정적으로 수행 하는 유일한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-170">For example, this technique is the only way to reliably perform [assert](using-the-assert-method.md) calls on multiple permissions in one method.</span></span> <span data-ttu-id="d0399-171"><xref:System.Security.PermissionSet> 및 <xref:System.Security.NamedPermissionSet> 클래스를 사용하여 권한 그룹을 만든 다음 적절한 메서드를 호출하여 원하는 보안 호출을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-171">Use the <xref:System.Security.PermissionSet> and <xref:System.Security.NamedPermissionSet> classes to create a group of permissions and then call the appropriate method to invoke the desired security call.</span></span>

<span data-ttu-id="d0399-172">명령적 구문을 사용하여 요구 및 재정의를 수행할 수 있지만 요청은 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-172">You can use imperative syntax to perform demands and overrides, but not requests.</span></span> <span data-ttu-id="d0399-173">권한 상태를 초기화하기 위해 필요한 정보가 런타임에만 알려지는 경우 선언적 구문 대신 명령적 구문을 요구 및 재정의에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-173">You might use imperative syntax for demands and overrides instead of declarative syntax when information that you need in order to initialize the permission state becomes known only at run time.</span></span> <span data-ttu-id="d0399-174">예를 들어 호출자에게 특정 파일을 읽을 수 있는 권한이 있도록 해야 하지만 런타임까지 해당 파일의 이름을 알 수 없는 경우 명령적 요구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-174">For example, if you want to ensure that callers have permission to read a certain file, but you do not know the name of that file until run time, use an imperative demand.</span></span> <span data-ttu-id="d0399-175">런타임에 조건이 유지되는지 및 테스트 결과에 따라 보안 요구를 수행할지 여부를 결정해야 하는 경우 선언적 검사 대신 명령적 검사를 사용하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-175">You might also choose to use imperative checks instead of declarative checks when you need to determine at run time whether a condition holds and, based on the result of the test, make a security demand (or not).</span></span>

<span data-ttu-id="d0399-176">다음 코드 조각에서는 코드의 호출자에게 `MyPermission`이라는 사용자 지정 권한이 있도록 요청하는 명령적 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-176">The following code fragment shows imperative syntax for requesting that your code's callers have a custom permission called `MyPermission`.</span></span> <span data-ttu-id="d0399-177">이 권한은 가상의 사용자 지정 권한이며 .NET Framework에 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-177">This permission is a hypothetical custom permission and does not exist in the .NET Framework.</span></span> <span data-ttu-id="d0399-178">`MyPermission`의 새 인스턴스가 `MyMethod`에서 생성되어 이 메서드만 보안 호출을 통해 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-178">A new instance of `MyPermission` is created in `MyMethod`, guarding only this method with the security call.</span></span>

```vb
Public Class MyClass1

   Public Sub New()

   End Sub

   Public Sub MyMethod()
      'MyPermission is demanded using imperative syntax.
      Dim Perm As New MyPermission()
      Perm.Demand()
      'This method is protected by the security call.
   End Sub

   Public Sub YourMethod()
      'YourMethod 'This method is not protected by the security call.
   End Sub
End Class
```

```csharp
public class MyClass {
   public MyClass(){

   }

   public void MyMethod() {
       //MyPermission is demanded using imperative syntax.
       MyPermission Perm = new MyPermission();
       Perm.Demand();
       //This method is protected by the security call.
   }

   public void YourMethod() {
       //This method is not protected by the security call.
   }
}
```

## <a name="using-managed-wrapper-classes"></a><span data-ttu-id="d0399-179">관리되는 래퍼 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="d0399-179">Using Managed Wrapper Classes</span></span>

<span data-ttu-id="d0399-180">대부분의 애플리케이션과 구성 요소(보안 라이브러리 제외)는 비관리 코드를 직접 호출하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-180">Most applications and components (except secure libraries) should not directly call unmanaged code.</span></span> <span data-ttu-id="d0399-181">여기에는 여러 가지 이유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-181">There are several reasons for this.</span></span> <span data-ttu-id="d0399-182">코드에서 비관리 코드를 직접 호출하는 경우 네이티브 코드를 호출하기 위해 코드에 높은 신뢰 수준이 부여되어야 하기 때문에 실행할 수 없는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-182">If code calls unmanaged code directly, it will not be allowed to run in many circumstances because code must be granted a high level of trust to call native code.</span></span> <span data-ttu-id="d0399-183">이러한 애플리케이션의 실행을 허용하도록 정책을 수정하면 시스템의 보안을 훨씬 약화되어 애플리케이션이 거의 모든 작업을 자유롭게 수행할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-183">If policy is modified to allow such an application to run, it can significantly weaken the security of the system, leaving the application free to perform almost any operation.</span></span>

<span data-ttu-id="d0399-184">또한 비관리 코드에 액세스할 수 있는 권한을 가진 코드에서 관리되지 않는 API를 호출하여 거의 모든 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-184">Additionally, code that has permission to access unmanaged code can probably perform almost any operation by calling into an unmanaged API.</span></span> <span data-ttu-id="d0399-185">예를 들어 비관리 코드를 호출할 수 있는 권한이 있는 코드는 <xref:System.Security.Permissions.FileIOPermission> 파일에 액세스할 필요가 없으며, **FileIOPermission**이 필요한 관리 되는 파일 api를 우회 하 여 관리 되지 않는 (WIN32) 파일 api를 직접 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-185">For example, code that has permission to call unmanaged code does not need <xref:System.Security.Permissions.FileIOPermission> to access a file; it can just call an unmanaged (Win32) file API directly, bypassing the managed file API that requires **FileIOPermission**.</span></span> <span data-ttu-id="d0399-186">관리 코드에 비관리 코드를 호출할 수 있는 권한이 있고 비관리 코드를 직접 호출하는 경우 런타임이 비관리 코드에 보안 제한을 적용할 수 없기 때문에 보안 시스템에서 이러한 제한을 안정적으로 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-186">If managed code has permission to call into unmanaged code and does call directly into unmanaged code, the security system will be unable to reliably enforce security restrictions, since the runtime cannot enforce such restrictions on unmanaged code.</span></span>

<span data-ttu-id="d0399-187">애플리케이션에서 비관리 코드에 액세스해야 하는 작업을 수행하려는 경우 필요한 기능을 래핑하는 신뢰할 수 있는 관리되는 클래스를 통해 수행해야 합니다(이러한 클래스가 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="d0399-187">If you want your application to perform an operation that requires accessing unmanaged code, it should do so through a trusted managed class that wraps the required functionality (if such a class exists).</span></span> <span data-ttu-id="d0399-188">보안 클래스 라이브러리에 이미 있는 경우 래퍼 클래스를 직접 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d0399-188">Do not create a wrapper class yourself if one already exists in a secure class library.</span></span> <span data-ttu-id="d0399-189">비관리 코드를 호출할 수 있도록 높은 신뢰 수준이 부여되어야 하는 래퍼 클래스는 호출자에게 적절한 권한이 있도록 요구해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-189">The wrapper class, which must be granted a high degree of trust to be allowed to make the call into unmanaged code, is responsible for demanding that its callers have the appropriate permissions.</span></span> <span data-ttu-id="d0399-190">래퍼 클래스를 사용하는 경우 코드에서 요청하기만 하면 래퍼 클래스가 요구하는 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0399-190">If you use the wrapper class, your code only needs to request and be granted the permissions that the wrapper class demands.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0399-191">참조</span><span class="sxs-lookup"><span data-stu-id="d0399-191">See also</span></span>

- <xref:System.Security.PermissionSet>
- <xref:System.Security.Permissions.FileIOPermission>
- <xref:System.Security.NamedPermissionSet>
- <xref:System.Security.Permissions.SecurityAction>
- [<span data-ttu-id="d0399-192">StartupExpression</span><span class="sxs-lookup"><span data-stu-id="d0399-192">Assert</span></span>](using-the-assert-method.md)
- [<span data-ttu-id="d0399-193">코드 액세스 보안</span><span class="sxs-lookup"><span data-stu-id="d0399-193">Code Access Security</span></span>](code-access-security.md)
- [<span data-ttu-id="d0399-194">코드 액세스 보안 기본 사항</span><span class="sxs-lookup"><span data-stu-id="d0399-194">Code Access Security Basics</span></span>](code-access-security-basics.md)
- [<span data-ttu-id="d0399-195">특성</span><span class="sxs-lookup"><span data-stu-id="d0399-195">Attributes</span></span>](../../standard/attributes/index.md)
- [<span data-ttu-id="d0399-196">메타데이터 및 자동 기술 구성 요소</span><span class="sxs-lookup"><span data-stu-id="d0399-196">Metadata and Self-Describing Components</span></span>](../../standard/metadata-and-self-describing-components.md)
