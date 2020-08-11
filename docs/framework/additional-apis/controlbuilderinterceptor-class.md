---
title: ControlBuilderInterceptor 클래스
ms.date: 08/11/2020
api_name:
- System.Web.Compilation.ControlBuilderInterceptor
api_location:
- System.Web.dll
api_type:
- Assembly
topic_type:
- apiref
ms.openlocfilehash: 312d977f832d262b1bebc6638280b67b133babdf
ms.sourcegitcommit: 70d6a7e4f7187cbfa332f0f8be76566f7828cfcd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/11/2020
ms.locfileid: "88084407"
---
# <a name="controlbuilderinterceptor-class"></a><span data-ttu-id="eccae-102">ControlBuilderInterceptor 클래스</span><span class="sxs-lookup"><span data-stu-id="eccae-102">ControlBuilderInterceptor class</span></span>

<span data-ttu-id="eccae-103">`ControlBuilderInterceptor`클래스를 사용 하면 컴파일 프로세스를 사용자 지정 하거나 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eccae-103">The `ControlBuilderInterceptor` class allows the compilation process to be customized or controlled.</span></span>

## <a name="syntax"></a><span data-ttu-id="eccae-104">구문</span><span class="sxs-lookup"><span data-stu-id="eccae-104">Syntax</span></span>

```csharp
internal class ControlBuilderInterceptor
```

> [!WARNING]
> <span data-ttu-id="eccae-105">`ControlBuilderInterceptor`클래스는 내부 클래스 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eccae-105">The `ControlBuilderInterceptor` class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="eccae-106">설명 섹션에 설명 된 대로이 형식의 존재를 확인 하 여 인터셉터 형식 지원이 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eccae-106">As described in the Remarks section, the existence of this type can be checked to determine whether interceptor type support is present.</span></span> <span data-ttu-id="eccae-107">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스의 다른 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eccae-107">Microsoft does not support any other use of this class in a production application under any circumstance.</span></span>

## <a name="remarks"></a><span data-ttu-id="eccae-108">설명</span><span class="sxs-lookup"><span data-stu-id="eccae-108">Remarks</span></span>

<span data-ttu-id="eccae-109">.NET Framework 2.0 및 .NET Framework 3.5에서 [8 월 2020](https://portal.msrc.microsoft.com/security-guidance/releasenotedetail/2020-Aug) 업데이트는 인터셉터 형식을 사용 하 여 컴파일 프로세스를 사용자 지정 하거나 제어 하는 지원을 추가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="eccae-109">In .NET Framework 2.0 and .NET Framework 3.5, the [August 2020](https://portal.msrc.microsoft.com/security-guidance/releasenotedetail/2020-Aug) updates added support for using an interceptor type to customize or control the compilation process.</span></span> <span data-ttu-id="eccae-110"><xref:System.Type.GetType?displayProperty=nameWithType> `ControlBuilderInterceptor` 다음 코드에 나와 있는 것 처럼을 사용 하 여 형식이 있는지 확인 하 여이 지원이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eccae-110">You can determine whether this support is present by using <xref:System.Type.GetType?displayProperty=nameWithType> to check the existence of the `ControlBuilderInterceptor` type, as demonstrated in the following code.</span></span>

```csharp
Type type = Type.GetType("System.Web.Compilation.ControlBuilderInterceptor, System.Web, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a");
```

<span data-ttu-id="eccae-111">반환 값이 null이 아닌 경우 인터셉터 지원이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eccae-111">If the return value is non-null, then interceptor support is present.</span></span> <span data-ttu-id="eccae-112">반환 값이 `null` 이거나 예외가 throw 되 면 8 월 2020 업데이트가 설치 되지 않은 것 이며 인터셉터 지원이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eccae-112">If the return value is `null`, or if an exception is thrown, then the August 2020 updates have not been installed, and interceptor support is absent.</span></span>

<span data-ttu-id="eccae-113">인터셉터 지원이 있는 경우에는 <xref:System.Web.Compilation.ControlBuilderInterceptor> 이후 버전의 .NET Framework와 동일 하 게 동일한 방법으로 컴파일 프로세스와 상호 작용 하는 인터셉터 형식을 작성 하 고 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eccae-113">If interceptor support is present, you can write and register an interceptor type that will interact with the compilation process in exactly the same way that <xref:System.Web.Compilation.ControlBuilderInterceptor> does on later versions of .NET Framework.</span></span> <span data-ttu-id="eccae-114">.NET Framework 2.0 및 .NET Framework 3.5에서 인터셉터 형식은 다음 요구 사항을 충족 하는 모든 클래스가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eccae-114">In .NET Framework 2.0 and .NET Framework 3.5, the interceptor type can be any class that meets the following requirements:</span></span>

* <span data-ttu-id="eccae-115">에는 매개 변수가 없는 public 생성자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eccae-115">Has a public, parameterless constructor.</span></span>
* <span data-ttu-id="eccae-116">에는 및 `PreControlBuilderInit` 메서드와 동일한 시그니처 및 의미 체계를 가진 및 라는 공용 비정적 메서드가 있으며,이 메서드는 `OnProcessGeneratedCode` <xref:System.Web.Compilation.ControlBuilderInterceptor.PreControlBuilderInit(System.Web.UI.ControlBuilder,System.Web.UI.TemplateParser,System.Web.UI.ControlBuilder,System.Type,System.String,System.String,System.Collections.IDictionary,System.Collections.IDictionary)> <xref:System.Web.Compilation.ControlBuilderInterceptor.OnProcessGeneratedCode(System.Web.UI.ControlBuilder,System.CodeDom.CodeCompileUnit,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeMemberMethod,System.CodeDom.CodeMemberMethod,System.Collections.IDictionary)> 이후 버전의 .NET Framework에 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="eccae-116">Has public, non-static methods named `PreControlBuilderInit` and `OnProcessGeneratedCode` that have the same signature and semantics as the <xref:System.Web.Compilation.ControlBuilderInterceptor.PreControlBuilderInit(System.Web.UI.ControlBuilder,System.Web.UI.TemplateParser,System.Web.UI.ControlBuilder,System.Type,System.String,System.String,System.Collections.IDictionary,System.Collections.IDictionary)> and <xref:System.Web.Compilation.ControlBuilderInterceptor.OnProcessGeneratedCode(System.Web.UI.ControlBuilder,System.CodeDom.CodeCompileUnit,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeMemberMethod,System.CodeDom.CodeMemberMethod,System.Collections.IDictionary)> methods, which exist in later versions of .NET Framework.</span></span>

<span data-ttu-id="eccae-117">`aspnet:20ControlBuilderInterceptor`ASP.NET 응용 프로그램 설정 ()의 키를 사용 하 여 인터셉터 형식을 등록 `<appSettings>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="eccae-117">Register the interceptor type by using the `aspnet:20ControlBuilderInterceptor` key in ASP.NET application settings (`<appSettings>`).</span></span> <span data-ttu-id="eccae-118">이 응용 프로그램 설정은 컴퓨터 또는 응용 프로그램 *web.config* 파일에 나열 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eccae-118">This application setting must be listed in your computer or application *web.config* file.</span></span> <span data-ttu-id="eccae-119">어셈블리의 정규화 된 형식 이름을 사용 하 여 인터셉터 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eccae-119">Specify the interceptor type by using its assembly-qualified type name.</span></span> <span data-ttu-id="eccae-120">다음 예제에서는 라는 인터셉터 형식을 등록 하는 방법을 보여 줍니다 `Fabrikam.Interceptor` .</span><span class="sxs-lookup"><span data-stu-id="eccae-120">The following example shows how to register an interceptor type named `Fabrikam.Interceptor`.</span></span>

```xml
<configuration>
  ...
  <appSettings>
    ...
    <add key="aspnet:20ControlBuilderInterceptor"
         value="Fabrikam.Interceptor, Fabrikam, Version=1.0.0.0, Culture=neutral, PublicKeyToken=2b3831f2f2b744f7" />
  </appSettings>
</configuration>

To retrieve the assembly-qualified name of a type, use the <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType> property, as demonstrated in the following code.

```csharp
string assemblyQualifiedName = typeof(Fabrikam.Interceptor).AssemblyQualifiedName;
```

<span data-ttu-id="eccae-121">인터셉터 지원이 있으면 컴파일 프로세스가 위에 설명 된 방식으로 나열 된 형식과 상호 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eccae-121">When interceptor support is present, the compilation process interacts with the listed type in the manner described above.</span></span> <span data-ttu-id="eccae-122">인터셉터 지원이 없으면 응용 프로그램 설정이 무시 되 고 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eccae-122">When interceptor support is absent, the application setting is ignored and has no effect.</span></span>

## <a name="requirements"></a><span data-ttu-id="eccae-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eccae-123">Requirements</span></span>

<span data-ttu-id="eccae-124">**네임 스페이스:** System.web. 컴파일</span><span class="sxs-lookup"><span data-stu-id="eccae-124">**Namespace:** System.Web.Compilation</span></span>

<span data-ttu-id="eccae-125">**어셈블리:** System.web (System.Web.dll)</span><span class="sxs-lookup"><span data-stu-id="eccae-125">**Assembly:** System.Web (in System.Web.dll)</span></span>

<span data-ttu-id="eccae-126">**.NET Framework 버전:** 3.5, 2.0</span><span class="sxs-lookup"><span data-stu-id="eccae-126">**.NET Framework versions:** 3.5, 2.0</span></span>
