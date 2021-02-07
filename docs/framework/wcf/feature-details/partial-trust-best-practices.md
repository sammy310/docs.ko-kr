---
description: '자세히 알아보기: 부분 신뢰 모범 사례'
title: 부분 신뢰를 위한 최선의 방법
ms.date: 03/30/2017
ms.assetid: 0d052bc0-5b98-4c50-8bb5-270cc8a8b145
ms.openlocfilehash: abdc0fbbb84581b302bca8d514a5f8f5cc2703e6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99733556"
---
# <a name="partial-trust-best-practices"></a><span data-ttu-id="efd9f-103">부분 신뢰를 위한 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="efd9f-103">Partial Trust Best Practices</span></span>

<span data-ttu-id="efd9f-104">이 항목에서는 부분 신뢰 환경에서 WCF (Windows Communication Foundation)를 실행할 때의 모범 사례를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-104">This topic describes best practices when running Windows Communication Foundation (WCF) in a partial trust environment.</span></span>

## <a name="serialization"></a><span data-ttu-id="efd9f-105">Serialization</span><span class="sxs-lookup"><span data-stu-id="efd9f-105">Serialization</span></span>

<span data-ttu-id="efd9f-106">부분 신뢰 애플리케이션에서 <xref:System.Runtime.Serialization.DataContractSerializer>를 사용할 때 다음 방법을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-106">Apply the following practices when using the <xref:System.Runtime.Serialization.DataContractSerializer> in a partially-trusted application.</span></span>

- <span data-ttu-id="efd9f-107">serialize할 수 있는 모든 형식은 명시적으로 `[DataContract]` 특성으로 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-107">All serializable types must be explicitly marked with the `[DataContract]` attribute.</span></span> <span data-ttu-id="efd9f-108">다음 기술은 부분 신뢰 환경에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-108">The following techniques are not supported in a partial trust environment:</span></span>

- <span data-ttu-id="efd9f-109">serialize할 클래스를 <xref:System.SerializableAttribute>로 표시하는 기술</span><span class="sxs-lookup"><span data-stu-id="efd9f-109">Marking classes to be serialized with the <xref:System.SerializableAttribute>.</span></span>

- <span data-ttu-id="efd9f-110">클래스가 serialization 프로세스를 제어할 수 있도록 <xref:System.Runtime.Serialization.ISerializable> 인터페이스를 구현하는 기술</span><span class="sxs-lookup"><span data-stu-id="efd9f-110">Implementing the <xref:System.Runtime.Serialization.ISerializable> interface to allow a class to control its serialization process.</span></span>

### <a name="using-datacontractserializer"></a><span data-ttu-id="efd9f-111">DataContractSerializer 사용</span><span class="sxs-lookup"><span data-stu-id="efd9f-111">Using DataContractSerializer</span></span>

- <span data-ttu-id="efd9f-112">`[DataContract]` 특성으로 표시된 형식은 모두 public이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-112">All types marked with the `[DataContract]` attribute must be public.</span></span> <span data-ttu-id="efd9f-113">public이 아닌 형식은 부분 신뢰 환경에서 serialize할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-113">Non-public types cannot be serialized in a partial trust environment.</span></span>

- <span data-ttu-id="efd9f-114">serialize할 수 있는 `[DataContract]` 형식의 모든 `[DataContract]` 멤버는 public이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-114">All `[DataContract]` members in a serializable `[DataContract]` type must be public.</span></span> <span data-ttu-id="efd9f-115">public이 아닌 `[DataMember]`가 있는 형식은 부분 신뢰 환경에서 serialize할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-115">A type with a non-public `[DataMember]` cannot be serialized in a partial trust environment.</span></span>

- <span data-ttu-id="efd9f-116">`OnSerializing`, `OnSerialized`, `OnDeserializing` 및 `OnDeserialized`와 같은 serialization 이벤트를 처리하는 메서드는 public으로 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-116">Methods that handle serialization events (such as `OnSerializing`, `OnSerialized`, `OnDeserializing`, and `OnDeserialized`) must be declared as public.</span></span> <span data-ttu-id="efd9f-117">그러나 <xref:System.Runtime.Serialization.IDeserializationCallback.OnDeserialization%28System.Object%29>의 명시적 구현과 암시적 구현이 모두 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-117">However, both explicit and implicit implementations of <xref:System.Runtime.Serialization.IDeserializationCallback.OnDeserialization%28System.Object%29> are supported.</span></span>

- <span data-ttu-id="efd9f-118">`[DataContract]`가 deserialization을 수행하는 동안 새로 인스턴스화된 개체의 생성자를 호출하지 않으므로 <xref:System.Security.AllowPartiallyTrustedCallersAttribute>로 표시된 어셈블리에서 구현한 <xref:System.Runtime.Serialization.DataContractSerializer> 형식은 형식 생성자에서 보안 관련 작업을 수행해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-118">`[DataContract]` types implemented in assemblies marked with the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> must not perform security-related actions in the type constructor, as the <xref:System.Runtime.Serialization.DataContractSerializer> does not call the constructor of the newly-instantiated object during deserialization.</span></span> <span data-ttu-id="efd9f-119">특히 다음과 같은 일반적인 보안 기술은 `[DataContract]` 형식에 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-119">Specifically, the following common security techniques must be avoided for `[DataContract]` types:</span></span>

- <span data-ttu-id="efd9f-120">형식 생성자를 internal 또는 private으로 설정하여 부분 신뢰 액세스를 제한하려고 시도하는 보안 기술</span><span class="sxs-lookup"><span data-stu-id="efd9f-120">Attempting to restrict partial trust access by making the type's constructor internal or private.</span></span>

- <span data-ttu-id="efd9f-121">`[LinkDemand]`를 형식 생성자에 추가하여 형식에 대한 액세스를 제한하는 보안 기술</span><span class="sxs-lookup"><span data-stu-id="efd9f-121">Restricting access to the type by adding a `[LinkDemand]` to the type's constructor.</span></span>

- <span data-ttu-id="efd9f-122">개체가 인스턴스화되었기 때문에 생성자가 적용한 유효성 검사가 확인되었다고 가정하는 보안 기술</span><span class="sxs-lookup"><span data-stu-id="efd9f-122">Assuming that because the object has been successfully instantiated, any validation checks enforced by the constructor have passed successfully.</span></span>

### <a name="using-ixmlserializable"></a><span data-ttu-id="efd9f-123">IXmlSerializable 사용</span><span class="sxs-lookup"><span data-stu-id="efd9f-123">Using IXmlSerializable</span></span>

<span data-ttu-id="efd9f-124">다음 최선의 방법은 <xref:System.Xml.Serialization.IXmlSerializable>을 구현하고 <xref:System.Runtime.Serialization.DataContractSerializer>를 사용하여 serialize되는 형식에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-124">The following best practices apply for types that implement <xref:System.Xml.Serialization.IXmlSerializable> and are serialized using the <xref:System.Runtime.Serialization.DataContractSerializer>:</span></span>

- <span data-ttu-id="efd9f-125"><xref:System.Xml.Serialization.IXmlSerializable.GetSchema%2A> 정적 메서드 구현에서는 `public`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-125">The <xref:System.Xml.Serialization.IXmlSerializable.GetSchema%2A> static method implementations must be `public`.</span></span>

- <span data-ttu-id="efd9f-126"><xref:System.Xml.Serialization.IXmlSerializable> 인터페이스를 구현하는 인스턴스 메서드는 `public`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-126">The instance methods that implement the <xref:System.Xml.Serialization.IXmlSerializable> interface must be `public`.</span></span>

## <a name="using-wcf-from-fully-trusted-platform-code-that-allows-calls-from-partially-trusted-callers"></a><span data-ttu-id="efd9f-127">부분적으로 신뢰하는 호출자의 호출을 허용하는 완전히 신뢰할 수 있는 플랫폼 코드에서 WCF 사용</span><span class="sxs-lookup"><span data-stu-id="efd9f-127">Using WCF from Fully-Trusted Platform Code that Allows Calls from Partially Trusted Callers</span></span>

<span data-ttu-id="efd9f-128">WCF 부분 신뢰 보안 모델은 WCF 공용 메서드 또는 속성의 호출자가 호스팅 응용 프로그램의 CAS (코드 액세스 보안) 컨텍스트에서 실행 되 고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-128">The WCF partial trust security model assumes that any caller of a WCF public method or property is running in the code access security (CAS) context of the hosting application.</span></span> <span data-ttu-id="efd9f-129">또한 WCF는 각각에 대해 하나의 응용 프로그램 보안 컨텍스트를가지고 있다고 가정 하 <xref:System.AppDomain> 고,이 컨텍스트는 <xref:System.AppDomain> 생성 시 신뢰할 수 있는 호스트 (예:에 대 한 호출 <xref:System.AppDomain.CreateDomain%2A> 또는 ASP.NET 응용 프로그램 관리자)에 의해 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-129">WCF also assumes that only one application security context exists for each <xref:System.AppDomain>, and that this context is established at <xref:System.AppDomain> creation time by a trusted host (for example, by a call to <xref:System.AppDomain.CreateDomain%2A> or by the ASP.NET Application Manager).</span></span>

<span data-ttu-id="efd9f-130">이 보안 모델은 보통 신뢰 ASP.NET 애플리케이션에서 실행되는 사용자 코드와 같은 추가 CAS 권한을 어설션할 수 없는 사용자가 작성한 애플리케이션에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-130">This security model applies to user-written applications that cannot assert additional CAS permissions, such as user code running in a Medium Trust ASP.NET application.</span></span> <span data-ttu-id="efd9f-131">그러나 완전히 신뢰할 수 있는 플랫폼 코드 (예: 전역 어셈블리 캐시에 설치 되 고 부분적으로 신뢰할 수 있는 코드의 호출을 허용 하는 타사 어셈블리)는 응용 프로그램 수준 보안 취약성을 방지 하기 위해 부분적으로 신뢰할 수 있는 응용 프로그램을 대신 하 여 WCF를 호출할 때 명시적인 주의가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-131">However, fully-trusted platform code (for example, a third-party assembly that is installed in the global assembly cache and accepts calls from partially-trusted code) must take explicit care when calling into WCF on behalf of a partially-trusted application to avoid introducing application-level security vulnerabilities.</span></span>

<span data-ttu-id="efd9f-132">완전 신뢰 코드는 <xref:System.Security.PermissionSet.Assert%2A> <xref:System.Security.PermissionSet.PermitOnly%2A> <xref:System.Security.PermissionSet.Deny%2A> 부분적으로 신뢰할 수 있는 코드를 대신 하 여 WCF api를 호출 하기 전에, 또는를 호출 하 여 현재 스레드의 CAS 권한 집합을 변경 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-132">Full-trust code should avoid altering the CAS permission set of the current thread (by calling <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.PermitOnly%2A>, or <xref:System.Security.PermissionSet.Deny%2A>) prior to calling WCF APIs on behalf of partially-trusted code.</span></span> <span data-ttu-id="efd9f-133">애플리케이션 수준 보안 컨텍스트와 독립적인 스레드 관련 권한 컨텍스트를 어설션하거나 거부하거나 만들면 예기치 않은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-133">Asserting, denying, or otherwise creating a thread-specific permission context that is independent of the application-level security context can result in unexpected behavior.</span></span> <span data-ttu-id="efd9f-134">애플리케이션에 따라 이 동작으로 인해 애플리케이션 수준의 보안이 취약해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-134">Depending on the application, this behavior may result in application-level security vulnerabilities.</span></span>

<span data-ttu-id="efd9f-135">스레드 특정 권한 컨텍스트를 사용 하 여 WCF를 호출 하는 코드는 다음과 같은 상황을 처리할 수 있도록 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-135">Code that calls into WCF using a thread-specific permission context must be prepared to handle the following situations that may arise:</span></span>

- <span data-ttu-id="efd9f-136">작업을 수행하는 동안 스레드 관련 보안 컨텍스트가 유지되지 않을 수 있으며, 이로 인해 잠재적인 보안 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-136">The thread-specific security context may not be maintained for the duration of the operation, which results in potential security exceptions.</span></span>

- <span data-ttu-id="efd9f-137">내부 WCF 코드 및 사용자가 제공한 콜백은 호출이 원래 시작 된 것과 다른 보안 컨텍스트에서 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-137">Internal WCF code as well as any user-provided callbacks may run in a different security context than the one under which the call was originally initiated.</span></span> <span data-ttu-id="efd9f-138">이러한 컨텍스트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-138">These contexts include:</span></span>

  - <span data-ttu-id="efd9f-139">애플리케이션 권한 컨텍스트</span><span class="sxs-lookup"><span data-stu-id="efd9f-139">The application permission context.</span></span>

  - <span data-ttu-id="efd9f-140">현재 실행 중인의 수명 동안 WCF를 호출 하는 데 사용 되는 다른 사용자 스레드에 의해 이전에 만든 모든 스레드 관련 권한 컨텍스트입니다 <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="efd9f-140">Any thread-specific permission context previously created by other user threads used to call into WCF during the lifetime of the currently running <xref:System.AppDomain>.</span></span>

<span data-ttu-id="efd9f-141">WCF는 WCF 공용 Api를 호출 하기 전에 완전히 신뢰할 수 있는 구성 요소에 의해 이러한 권한이 어설션 되지 않는 한 부분적으로 신뢰할 수 있는 코드를 완전 신뢰 권한으로 가져올 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-141">WCF guarantees that partially-trusted code cannot obtain full-trust permissions unless such permissions are asserted by a fully-trusted component prior to calling into WCF public APIs.</span></span> <span data-ttu-id="efd9f-142">그러나 완전 신뢰 권한의 어설션 결과가 특정 스레드, 작업 또는 사용자 작업에만 적용되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-142">However, it does not guarantee that the effects of asserting full trust is isolated to a particular thread, operation, or user action.</span></span>

<span data-ttu-id="efd9f-143">가장 좋은 방법은 <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.PermitOnly%2A> 또는 <xref:System.Security.PermissionSet.Deny%2A>를 호출하여 스레드 관련 권한 컨텍스트를 만들지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-143">As a best practice, avoid creating thread-specific permission context by calling <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.PermitOnly%2A>, or <xref:System.Security.PermissionSet.Deny%2A>.</span></span> <span data-ttu-id="efd9f-144">대신 애플리케이션 자체에 권한을 부여하거나 거부하면 <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.Deny%2A> 또는 <xref:System.Security.PermissionSet.PermitOnly%2A>가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efd9f-144">Instead, grant or deny the privilege to the application itself, so that no <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.Deny%2A>, or <xref:System.Security.PermissionSet.PermitOnly%2A> is required.</span></span>

## <a name="see-also"></a><span data-ttu-id="efd9f-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="efd9f-145">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Xml.Serialization.IXmlSerializable>
