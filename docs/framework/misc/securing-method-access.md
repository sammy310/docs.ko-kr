---
title: 메서드 액세스 보안
description: 공용으로 사용 하기에 적합 하지 않지만 여전히 public 이어야 하는 메서드에 대해 메서드 액세스를 안전 하 게 만드는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- code security, method access
- secure coding, method access
- security [.NET Framework], method access
- method access security
ms.assetid: f7c2d6ec-3b18-4e0e-9991-acd97189d818
ms.openlocfilehash: a7ef419cf3959cf7a3ffde874353dacd3815c81a
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309393"
---
# <a name="securing-method-access"></a><span data-ttu-id="bc077-103">메서드 액세스 보안</span><span class="sxs-lookup"><span data-stu-id="bc077-103">Securing Method Access</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="bc077-104">몇몇 메서드는 임의의 신뢰할 수 없는 코드 호출을 허용하는 데 적합하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-104">Some methods might not be suitable to allow arbitrary untrusted code to call.</span></span> <span data-ttu-id="bc077-105">이러한 메서드는 위험을 가져옵니다. 메서드가 제한된 정보를 제공하거나, 전달된 임의 정보를 신뢰하거나, 매개 변수에서 오류 검사를 수행하지 않거나, 잘못된 매개 변수를 사용하여 오작동하거나 피해를 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-105">Such methods pose several risks: The method might provide some restricted information; it might believe any information passed to it; it might not do error checking on the parameters; or with the wrong parameters, it might malfunction or do something harmful.</span></span> <span data-ttu-id="bc077-106"> 이들 경우에 대해 알고 있어야 하고 메서드 보호를 도와주는 조치를 취해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-106">You should be aware of these cases and take action to help protect the method.</span></span>  
  
 <span data-ttu-id="bc077-107">경우에 따라 공용으로 제공되지 않지만 공용으로 사용되어야 하는 메서드를 제한해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-107">In some cases, you might need to restrict methods that are not intended for public use but still must be public.</span></span> <span data-ttu-id="bc077-108">예를 들어 자체 DLL에서 호출되어야 하고 공용으로도 사용되어야 하는 인터페이스를 포함하지만, 이 인터페이스를 고객이 사용하지 않도록 하고 악성 코드가 구성 요소에 대한 진입점으로 악용하지 못하도록 방지하기 위해 이 인터페이스를 공개적으로 노출하지 않고자 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-108">For example, you might have an interface that needs to be called across your own DLLs and hence must be public, but you do not want to expose it publicly to prevent customers from using it or to prevent malicious code from exploiting the entry point into your component.</span></span> <span data-ttu-id="bc077-109">공용으로 사용 하기에 적합 하지 않은 메서드를 제한 하는 또 다른 일반적인 이유는 내부 인터페이스 일 수 있는 항목을 문서화 하 고 지원할 필요가 없도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-109">Another common reason to restrict a method not intended for public use (but that must be public) is to avoid having to document and support what might be an internal interface.</span></span>  
  
 <span data-ttu-id="bc077-110">관리 코드는 메서드 액세스를 제한하는 여러 가지 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-110">Managed code offers several ways to restrict method access:</span></span>  
  
- <span data-ttu-id="bc077-111">액세스 가능성 범위를 신뢰할 수 있는 클래스, 어셈블리 또는 파생 클래스로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-111">Limit the scope of accessibility to the class, assembly, or derived classes, if they can be trusted.</span></span> <span data-ttu-id="bc077-112">이는 메서드 액세스를 제한하는 가장 간단한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-112">This is the simplest way to limit method access.</span></span> <span data-ttu-id="bc077-113">일반적으로 파생 클래스는 부모 클래스의 id를 공유 하는 경우 파생 클래스는 파생 클래스에서 파생 된 클래스 보다 신뢰 수준이 떨어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-113">In general, derived classes can be less trustworthy than the class they derive from, though in some cases they share the parent class's identity.</span></span> <span data-ttu-id="bc077-114">특히 `protected` 보안 컨텍스트에서 반드시 사용 되는 것은 아니므로 키워드에서 트러스트를 유추 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="bc077-114">In particular, do not infer trust from the keyword `protected`, which is not necessarily used in the security context.</span></span>  
  
- <span data-ttu-id="bc077-115">지정 된 id의 호출자에 대 한 액세스 권한을 제한 합니다. 기본적으로 특정 [증명 정보](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7y5x1hcd%28v=vs.100%29) (강력한 이름, 게시자, 영역 등)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-115">Limit the method access to callers of a specified identity--essentially, any particular [evidence](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7y5x1hcd%28v=vs.100%29) (strong name, publisher, zone, and so on) you choose.</span></span>  
  
- <span data-ttu-id="bc077-116">메서드 액세스를 선택한 권한을 가진 호출자로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-116">Limit the method access to callers having whatever permissions you select.</span></span>  
  
 <span data-ttu-id="bc077-117">마찬가지로 선언적 보안을 통해 클래스 상속을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-117">Similarly, declarative security allows you to control inheritance of classes.</span></span> <span data-ttu-id="bc077-118">**InheritanceDemand** 를 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-118">You can use **InheritanceDemand** to do the following:</span></span>  
  
- <span data-ttu-id="bc077-119">지정된 ID 또는 권한을 포함할 파생 클래스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-119">Require derived classes to have a specified identity or permission.</span></span>  
  
- <span data-ttu-id="bc077-120">지정된 ID 또는 권한을 포함하도록 특정 메서드를 재정의하는 파생 클래스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-120">Require derived classes that override specific methods to have a specified identity or permission.</span></span>  
  
 <span data-ttu-id="bc077-121">다음 예제에서는 특정 강력한 이름을 통해 호출자에 서명하도록 요구하여 제한된 액세스용 공용 클래스를 보호하도록 도와주는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-121">The following example shows how to help protect a public class for limited access by requiring that callers be signed with a particular strong name.</span></span> <span data-ttu-id="bc077-122">이 예제에서는 <xref:System.Security.Permissions.StrongNameIdentityPermissionAttribute> 강력한 이름에 대 한 **요청과** 함께를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-122">This example uses the <xref:System.Security.Permissions.StrongNameIdentityPermissionAttribute> with a **Demand** for the strong name.</span></span> <span data-ttu-id="bc077-123">강력한 이름을 사용 하 여 어셈블리에 서명 하는 방법에 대 한 작업 기반 정보는 [강력한 이름의 어셈블리 만들기 및 사용](../../standard/assembly/create-use-strong-named.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc077-123">For task-based information on how to sign an assembly with a strong name, see [Creating and Using Strong-Named Assemblies](../../standard/assembly/create-use-strong-named.md).</span></span>  
  
```vb  
<StrongNameIdentityPermissionAttribute(SecurityAction.Demand, PublicKey := "…hex…", Name := "App1", Version := "0.0.0.0")>  _  
Public Class Class1  
End Class  
```  
  
```csharp  
[StrongNameIdentityPermissionAttribute(SecurityAction.Demand, PublicKey="…hex…", Name="App1", Version="0.0.0.0")]  
public class Class1  
{  
  
}
```  
  
## <a name="excluding-classes-and-members-from-use-by-untrusted-code"></a><span data-ttu-id="bc077-124">신뢰할 수 없는 코드에 의한 클래스 및 멤버 사용 방지</span><span class="sxs-lookup"><span data-stu-id="bc077-124">Excluding Classes and Members from Use by Untrusted Code</span></span>  
 <span data-ttu-id="bc077-125">이 섹션에 표시된 선언을 사용하여 특정 클래스와 메서드 및 속성과 이벤트가 부분 신뢰 코드에서 사용되지 않도록 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-125">Use the declarations shown in this section to prevent specific classes and methods, as well as properties and events, from being used by partially trusted code.</span></span> <span data-ttu-id="bc077-126">이러한 선언을 클래스에 적용 하 여 모든 메서드, 속성 및 이벤트에 대 한 보호를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-126">By applying these declarations to a class, you apply the protection to all its methods, properties, and events.</span></span> <span data-ttu-id="bc077-127">그러나 필드 액세스는 선언적 보안의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-127">However, field access is not affected by declarative security.</span></span> <span data-ttu-id="bc077-128">또한 링크 요청은 직접 실행 호출자 차단에만 도움이 되고 유인 공격의 대상이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-128">Note also that link demands help protect against only the immediate callers and might still be subject to luring attacks.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bc077-129">새 투명도 모델은 .NET Framework 4에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-129">A new transparency model has been introduced in the .NET Framework 4.</span></span> <span data-ttu-id="bc077-130">[보안 투명 코드, 수준 2](security-transparent-code-level-2.md) 모델은 특성을 사용 하 여 보안 코드를 식별 합니다 <xref:System.Security.SecurityCriticalAttribute> .</span><span class="sxs-lookup"><span data-stu-id="bc077-130">The [Security-Transparent Code, Level 2](security-transparent-code-level-2.md) model identifies secure code with the <xref:System.Security.SecurityCriticalAttribute> attribute.</span></span> <span data-ttu-id="bc077-131">보안에 중요한 코드에서는 호출자와 상속자를 둘 다 완전히 신뢰할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-131">Security-critical code requires both callers and inheritors to be fully trusted.</span></span> <span data-ttu-id="bc077-132">이전 .NET Framework 버전에서 코드 액세스 보안 규칙에 따라 실행 중인 어셈블리는 수준 2 어셈블리를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-132">Assemblies that are running under the code access security rules from earlier .NET Framework versions can call level 2 assemblies.</span></span> <span data-ttu-id="bc077-133">이 경우 보안에 중요한 특성은 완전 신뢰를 위해 링크 요청으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-133">In this case, the security-critical attributes will be treated as link demands for full trust.</span></span>  
  
 <span data-ttu-id="bc077-134">강력한 이름의 어셈블리에서 [LinkDemand](link-demands.md) 는 완전히 신뢰할 수 있는 호출자에 게 사용을 제한 하기 위해 공개적으로 액세스할 수 있는 모든 메서드, 속성 및 이벤트에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-134">In strong-named assemblies, a [LinkDemand](link-demands.md) is applied to all publicly accessible methods, properties, and events therein to restrict their use to fully trusted callers.</span></span> <span data-ttu-id="bc077-135">이 기능을 사용하지 않도록 설정하려면 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 특성을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-135">To disable this feature, you must apply the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute.</span></span> <span data-ttu-id="bc077-136">따라서 신뢰할 수 없는 호출자를 제외하도록 클래스에 명시적으로 표시하는 작업은 서명되지 않은 어셈블리나 이 특성이 포함된 어셈블리에만 필요합니다. 이들 선언을 사용하여 신뢰할 수 없는 호출자로 제공되지 않은 형식 하위 집합을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-136">Thus, explicitly marking classes to exclude untrusted callers is necessary only for unsigned assemblies or assemblies with this attribute; you can use these declarations to mark a subset of types therein that are not intended for untrusted callers.</span></span>  
  
 <span data-ttu-id="bc077-137">다음 예제에서는 클래스와 멤버가 신뢰할 수 없는 코드에서 사용되지 않도록 방지하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-137">The following examples show how to prevent classes and members from being used by untrusted code.</span></span>  
  
 <span data-ttu-id="bc077-138">봉인되지 않은 공용 클래스의 경우:</span><span class="sxs-lookup"><span data-stu-id="bc077-138">For public nonsealed classes:</span></span>  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name := "FullTrust"), _
System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _  
Public Class CanDeriveFromMe  
End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
public class CanDeriveFromMe  
{  
}  
```  
  
 <span data-ttu-id="bc077-139">봉인된 공용 클래스의 경우:</span><span class="sxs-lookup"><span data-stu-id="bc077-139">For public sealed classes:</span></span>  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _  
NotInheritable Public Class CannotDeriveFromMe  
End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
public sealed class CannotDeriveFromMe  
{  
}  
```  
  
 <span data-ttu-id="bc077-140">공용 추상 클래스의 경우:</span><span class="sxs-lookup"><span data-stu-id="bc077-140">For public abstract classes:</span></span>  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name := "FullTrust"), _  
System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _  
MustInherit Public Class CannotCreateInstanceOfMe_CanCastToMe  
End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
public abstract class CannotCreateInstanceOfMe_CanCastToMe {}  
```  
  
 <span data-ttu-id="bc077-141">공용 가상 함수의 경우:</span><span class="sxs-lookup"><span data-stu-id="bc077-141">For public virtual functions:</span></span>  
  
```vb  
Class Base1
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _  
    Public Overridable Sub CanOverrideOrCallMe()  
    End Sub 'CanOverrideOrCallMe  
End Class 'Base1  
```  
  
```csharp  
class Base1
{  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
    public virtual void CanOverrideOrCallMe() {}  
}  
```  
  
 <span data-ttu-id="bc077-142">공용 추상 함수의 경우:</span><span class="sxs-lookup"><span data-stu-id="bc077-142">For public abstract functions:</span></span>  
  
```vb  
MustInherit Class Base2  
    <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _  
    Public Sub MustOverrideMe()  
    End Sub  
End Class 'Base2  
```  
  
```csharp  
abstract class Base2 {  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
public abstract void MustOverrideMe();  
}  
```  
  
 <span data-ttu-id="bc077-143">기본 클래스가 완전 신뢰를 요청하지 않는 공용 재정의 함수의 경우:</span><span class="sxs-lookup"><span data-stu-id="bc077-143">For public override functions where the base class does not demand full trust:</span></span>  
  
```vb  
Class Derived  
    Inherits Base1  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.Demand, Name:="FullTrust")> _  
    Public Overrides Sub CanOverrideOrCallMe()  
        MyBase.CanOverrideOrCallMe()  
    End Sub 'CanOverrideOrCallMe  
End Class 'Derived  
```  
  
```csharp  
class Derived : Base1  
{
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.Demand, Name="FullTrust")]
    public override void CanOverrideOrCallMe()
    {  
        base.CanOverrideOrCallMe();  
    }  
}  
```  
  
 <span data-ttu-id="bc077-144">기본 클래스가 완전 신뢰를 요청하는 공용 재정의 함수의 경우:</span><span class="sxs-lookup"><span data-stu-id="bc077-144">For public override functions where the base class demands full trust:</span></span>  
  
```vb  
Class Derived  
    Inherits Base1  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _  
    Public Overrides Sub CanOverrideOrCallMe()  
        MyBase.CanOverrideOrCallMe()  
    End Sub 'CanOverrideOrCallMe
End Class 'Derived  
```  
  
```csharp  
class Derived : Base1  
{
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]
    public override void CanOverrideOrCallMe()
    {  
        base.CanOverrideOrCallMe();  
    }  
}  
```  
  
 <span data-ttu-id="bc077-145">공용 인터페이스의 경우:</span><span class="sxs-lookup"><span data-stu-id="bc077-145">For public interfaces:</span></span>  
  
```vb  
Public Interface ICanCastToMe  
    <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust")> _  
    Sub CanImplementMe()  
End Interface 'ICanCastToMe  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust")> _  
Class Implemented  
    Implements ICanCastToMe  
    Public Sub CanImplementMe()  
    End Sub 'CanImplementMe  
```  
  
```csharp  
public interface ICanCastToMe
{  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")]  
void CanImplementMe();  
}  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")]  
class Implemented : ICanCastToMe  
{  
    public void CanImplementMe()  
    {  
    }  
}  
```  
  
## <a name="virtual-internal-overrides-or-overloads-overridable-friend"></a><span data-ttu-id="bc077-146">Virtual Internal 재정의 또는 Overloads Overridable Friend</span><span class="sxs-lookup"><span data-stu-id="bc077-146">Virtual Internal Overrides or Overloads Overridable Friend</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bc077-147">이 섹션에서는 메서드를 `virtual` 및 `internal` (Visual Basic)로 선언할 때 발생 하는 보안 문제에 대해 경고 `Overloads` `Overridable` `Friend` 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-147">This section warns about a security issue when declaring a method as both `virtual` and `internal` (`Overloads` `Overridable` `Friend` in Visual Basic).</span></span> <span data-ttu-id="bc077-148">이 경고는 .NET Framework 버전 1.0 및 1.1에만 적용 되 고 이후 버전에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-148">This warning applies only to the .NET Framework versions 1.0 and 1.1, it does not apply to later versions.</span></span>  
  
 <span data-ttu-id="bc077-149">.NET Framework 버전 1.0 및 1.1에서는 다른 어셈블리에서 코드를 사용할 수 없다는 것을 확인 하는 경우 형식 시스템 액세스 가능성의 nuance에 대해 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-149">In the .NET Framework versions 1.0 and 1.1, you must be aware of a nuance of the type system accessibility when confirming that your code is unavailable to other assemblies.</span></span> <span data-ttu-id="bc077-150">**가상** 및 **내부** (Visual Basic의**재정의 가능한 Friend** )로 선언 된 메서드는 부모 클래스의 vtable 항목을 재정의할 수 있으며 내부 이기 때문에 동일한 어셈블리 내 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-150">A method that is declared **virtual** and **internal** (**Overloads Overridable Friend** in Visual Basic) can override the parent class's vtable entry and can be used only from within the same assembly because it is internal.</span></span> <span data-ttu-id="bc077-151">그러나 재정의할 수 있는 액세스 가능성은 **virtual** 키워드에 의해 결정 되며, 해당 코드가 클래스 자체에 액세스할 수 있는 한 다른 어셈블리에서 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-151">However, the accessibility for overriding is determined by the **virtual** keyword, and this can be overridden from another assembly as long as that code has access to the class itself.</span></span> <span data-ttu-id="bc077-152">재정의가 문제를 발생 시킬 가능성이 있는 경우 선언적 보안을 사용 하 여 문제를 해결 하거나, 꼭 필요 하지 않은 경우 **가상** 키워드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-152">If the possibility of an override presents a problem, use declarative security to fix it, or remove the **virtual** keyword if it is not strictly required.</span></span>  
  
 <span data-ttu-id="bc077-153">언어 컴파일러에서 컴파일 오류가 발생 하 여 이러한 재정의를 방지 하는 경우에도 다른 컴파일러를 사용 하 여 작성 된 코드를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc077-153">Even if a language compiler prevents these overrides with a compilation error, it is possible for code written with other compilers to override.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc077-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc077-154">See also</span></span>

- [<span data-ttu-id="bc077-155">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="bc077-155">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
