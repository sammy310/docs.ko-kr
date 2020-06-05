---
title: 공통 특성
ms.date: 07/20/2015
ms.assetid: 11fe4894-1bf9-4525-a36b-cddcd3a5d22b
ms.openlocfilehash: 57ef8f103d64a51d896f46d2889d78ec99ff3223
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400721"
---
# <a name="common-attributes-visual-basic"></a><span data-ttu-id="9abe0-102">일반 특성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9abe0-102">Common Attributes (Visual Basic)</span></span>

<span data-ttu-id="9abe0-103">이 항목에서는 Visual Basic 프로그램에서 가장 일반적으로 사용 되는 특성에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-103">This topic describes the attributes that are most commonly used in Visual Basic programs.</span></span>

- [<span data-ttu-id="9abe0-104">전역 특성</span><span class="sxs-lookup"><span data-stu-id="9abe0-104">Global Attributes</span></span>](#Global)

- [<span data-ttu-id="9abe0-105">사용되지 않는 특성</span><span class="sxs-lookup"><span data-stu-id="9abe0-105">Obsolete Attribute</span></span>](#Obsolete)

- [<span data-ttu-id="9abe0-106">조건부 특성</span><span class="sxs-lookup"><span data-stu-id="9abe0-106">Conditional Attribute</span></span>](#Conditional)

- [<span data-ttu-id="9abe0-107">호출자 정보 특성</span><span class="sxs-lookup"><span data-stu-id="9abe0-107">Caller Info Attributes</span></span>](#CallerInfo)

- [<span data-ttu-id="9abe0-108">Visual Basic 특성</span><span class="sxs-lookup"><span data-stu-id="9abe0-108">Visual Basic Attributes</span></span>](#VB)

## <a name="global-attributes"></a><a name="Global"></a><span data-ttu-id="9abe0-109">전역 특성</span><span class="sxs-lookup"><span data-stu-id="9abe0-109">Global Attributes</span></span>

<span data-ttu-id="9abe0-110">대부분의 특성은 클래스나 메서드와 같은 특정 언어 요소에 적용되지만 일부 특성은 전체 어셈블리나 모듈에 적용되는 전역 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-110">Most attributes are applied to specific language elements such as classes or methods; however, some attributes are global—they apply to an entire assembly or module.</span></span> <span data-ttu-id="9abe0-111">예를 들어 다음과 같이 <xref:System.Reflection.AssemblyVersionAttribute> 특성을 사용하여 버전 정보를 어셈블리에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-111">For example, the <xref:System.Reflection.AssemblyVersionAttribute> attribute can be used to embed version information into an assembly, like this:</span></span>

```vb
<Assembly: AssemblyVersion("1.0.0.0")>
```

<span data-ttu-id="9abe0-112">전역 특성은 소스 코드에서 최상위 `Imports` 문과 모든 형식, 모듈 또는 네임 스페이스 선언 앞에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-112">Global attributes appear in the source code after any top-level `Imports` statements and before any type, module, or namespace declarations.</span></span> <span data-ttu-id="9abe0-113">전역 특성은 여러 소스 파일에 나타날 수 있지만 파일은 하나의 컴파일 패스에서 컴파일되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-113">Global attributes can appear in multiple source files, but the files must be compiled in a single compilation pass.</span></span> <span data-ttu-id="9abe0-114">Visual Basic 프로젝트의 경우 일반적으로 전역 특성은 AssemblyInfo 파일에 저장 됩니다 .이 파일은 Visual Studio에서 프로젝트를 만들 때 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-114">For Visual Basic projects, global attributes are generally put in the AssemblyInfo.vb file (the file is created automatically when you create a project in Visual Studio).</span></span>

<span data-ttu-id="9abe0-115">어셈블리 특성은 어셈블리에 대한 정보를 제공하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-115">Assembly attributes are values that provide information about an assembly.</span></span> <span data-ttu-id="9abe0-116">어셈블리 특성은 다음 범주로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-116">They fall into the following categories:</span></span>

- <span data-ttu-id="9abe0-117">어셈블리 ID 특성</span><span class="sxs-lookup"><span data-stu-id="9abe0-117">Assembly identity attributes</span></span>

- <span data-ttu-id="9abe0-118">정보 특성</span><span class="sxs-lookup"><span data-stu-id="9abe0-118">Informational attributes</span></span>

- <span data-ttu-id="9abe0-119">어셈블리 매니페스트 특성</span><span class="sxs-lookup"><span data-stu-id="9abe0-119">Assembly manifest attributes</span></span>

### <a name="assembly-identity-attributes"></a><span data-ttu-id="9abe0-120">어셈블리 ID 특성</span><span class="sxs-lookup"><span data-stu-id="9abe0-120">Assembly Identity Attributes</span></span>

<span data-ttu-id="9abe0-121">name, version 및 culture의 세 가지 특성(해당하는 경우 강력한 이름 포함)이 어셈블리의 ID를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-121">Three attributes (with a strong name, if applicable) determine the identity of an assembly: name, version, and culture.</span></span> <span data-ttu-id="9abe0-122">이러한 특성은 어셈블리의 전체 이름을 구성하며 코드에서 어셈블리를 참조할 때 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-122">These attributes form the full name of the assembly and are required when you reference it in code.</span></span> <span data-ttu-id="9abe0-123">특성을 사용하여 어셈블리의 버전 및 문화권을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-123">You can set an assembly's version and culture using attributes.</span></span> <span data-ttu-id="9abe0-124">그러나 이름 값은 어셈블리가 만들어질 때 어셈블리 매니페스트가 포함된 파일에 따라 컴파일러, [어셈블리 정보 대화 상자](/visualstudio/ide/reference/assembly-information-dialog-box)의 Visual Studio IDE 또는 어셈블리 링커(Al.exe)에서 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-124">However, the name value is set by the compiler, the Visual Studio IDE in the [Assembly Information Dialog Box](/visualstudio/ide/reference/assembly-information-dialog-box), or the Assembly Linker (Al.exe) when the assembly is created, based on the file that contains the assembly manifest.</span></span> <span data-ttu-id="9abe0-125"><xref:System.Reflection.AssemblyFlagsAttribute> 특성은 어셈블리의 여러 복사본이 공존할 수 있는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-125">The <xref:System.Reflection.AssemblyFlagsAttribute> attribute specifies whether multiple copies of the assembly can coexist.</span></span>

<span data-ttu-id="9abe0-126">다음 표에서는 ID 특성들을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-126">The following table shows the identity attributes.</span></span>

|<span data-ttu-id="9abe0-127">특성</span><span class="sxs-lookup"><span data-stu-id="9abe0-127">Attribute</span></span>|<span data-ttu-id="9abe0-128">용도</span><span class="sxs-lookup"><span data-stu-id="9abe0-128">Purpose</span></span>|
|---------------|-------------|
|<xref:System.Reflection.AssemblyName>|<span data-ttu-id="9abe0-129">어셈블리의 ID를 모두 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-129">Fully describes the identity of an assembly.</span></span>|
|<xref:System.Reflection.AssemblyVersionAttribute>|<span data-ttu-id="9abe0-130">어셈블리의 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-130">Specifies the version of an assembly.</span></span>|
|<xref:System.Reflection.AssemblyCultureAttribute>|<span data-ttu-id="9abe0-131">어셈블리에서 지원하는 문화권을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-131">Specifies which culture the assembly supports.</span></span>|
|<xref:System.Reflection.AssemblyFlagsAttribute>|<span data-ttu-id="9abe0-132">어셈블리가 같은 컴퓨터, 같은 프로세스 또는 같은 애플리케이션 도메인에서 Side-by-side 실행을 지원하는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-132">Specifies whether an assembly supports side-by-side execution on the same computer, in the same process, or in the same application domain.</span></span>|

### <a name="informational-attributes"></a><span data-ttu-id="9abe0-133">정보 특성</span><span class="sxs-lookup"><span data-stu-id="9abe0-133">Informational Attributes</span></span>

<span data-ttu-id="9abe0-134">정보 특성을 사용하여 어셈블리와 연관된 회사 또는 제품에 대한 추가적인 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-134">You can use informational attributes to provide additional company or product information for an assembly.</span></span> <span data-ttu-id="9abe0-135">다음 표에서는 <xref:System.Reflection?displayProperty=nameWithType> 네임스페이스에 정의된 정보 특성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-135">The following table shows the informational attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>

|<span data-ttu-id="9abe0-136">특성</span><span class="sxs-lookup"><span data-stu-id="9abe0-136">Attribute</span></span>|<span data-ttu-id="9abe0-137">용도</span><span class="sxs-lookup"><span data-stu-id="9abe0-137">Purpose</span></span>|
|---------------|-------------|
|<xref:System.Reflection.AssemblyProductAttribute>|<span data-ttu-id="9abe0-138">어셈블리 매니페스트에 대한 제품 이름을 지정하는 사용자 지정 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-138">Defines a custom attribute that specifies a product name for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyTrademarkAttribute>|<span data-ttu-id="9abe0-139">어셈블리 매니페스트에 대한 상표를 지정하는 사용자 지정 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-139">Defines a custom attribute that specifies a trademark for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|<span data-ttu-id="9abe0-140">어셈블리 매니페스트에 대한 정보 버전을 지정하는 사용자 지정 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-140">Defines a custom attribute that specifies an informational version for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyCompanyAttribute>|<span data-ttu-id="9abe0-141">어셈블리 매니페스트에 대한 회사 이름을 지정하는 사용자 지정 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-141">Defines a custom attribute that specifies a company name for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyCopyrightAttribute>|<span data-ttu-id="9abe0-142">어셈블리 매니페스트에 대한 저작권을 지정하는 사용자 지정 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-142">Defines a custom attribute that specifies a copyright for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyFileVersionAttribute>|<span data-ttu-id="9abe0-143">Win32 파일 버전 리소스에 대한 특정 버전 번호를 사용하도록 컴파일러에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-143">Instructs the compiler to use a specific version number for the Win32 file version resource.</span></span>|
|<xref:System.CLSCompliantAttribute>|<span data-ttu-id="9abe0-144">어셈블리가 CLS(공용 언어 사양)을 준수하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-144">Indicates whether the assembly is compliant with the Common Language Specification (CLS).</span></span>|

### <a name="assembly-manifest-attributes"></a><span data-ttu-id="9abe0-145">어셈블리 매니페스트 특성</span><span class="sxs-lookup"><span data-stu-id="9abe0-145">Assembly Manifest Attributes</span></span>

<span data-ttu-id="9abe0-146">어셈블리 매니페스트 특성을 사용하여 어셈블리 매니페스트의 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-146">You can use assembly manifest attributes to provide information in the assembly manifest.</span></span> <span data-ttu-id="9abe0-147">정보에는 제목, 설명, 기본 별칭 및 구성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-147">This includes title, description, default alias, and configuration.</span></span> <span data-ttu-id="9abe0-148">다음 표에서는 <xref:System.Reflection?displayProperty=nameWithType> 네임스페이스에 정의된 어셈블리 매니페스트 특성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-148">The following table shows the assembly manifest attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>

|<span data-ttu-id="9abe0-149">특성</span><span class="sxs-lookup"><span data-stu-id="9abe0-149">Attribute</span></span>|<span data-ttu-id="9abe0-150">용도</span><span class="sxs-lookup"><span data-stu-id="9abe0-150">Purpose</span></span>|
|---------------|-------------|
|<xref:System.Reflection.AssemblyTitleAttribute>|<span data-ttu-id="9abe0-151">어셈블리 매니페스트에 대한 어셈블리 제목을 지정하는 사용자 지정 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-151">Defines a custom attribute that specifies an assembly title for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyDescriptionAttribute>|<span data-ttu-id="9abe0-152">어셈블리 매니페스트에 대한 어셈블리 설명을 지정하는 사용자 지정 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-152">Defines a custom attribute that specifies an assembly description for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyConfigurationAttribute>|<span data-ttu-id="9abe0-153">어셈블리 매니페스트에 대한 어셈블리 구성(예: 정품 또는 디버그)을 지정하는 사용자 지정 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-153">Defines a custom attribute that specifies an assembly configuration (such as retail or debug) for an assembly manifest.</span></span>|
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|<span data-ttu-id="9abe0-154">어셈블리 매니페스트에 대한 친숙한 기본 별칭을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-154">Defines a friendly default alias for an assembly manifest</span></span>|

## <a name="obsolete-attribute"></a><a name="Obsolete"></a> <span data-ttu-id="9abe0-155">사용되지 않는 특성</span><span class="sxs-lookup"><span data-stu-id="9abe0-155">Obsolete Attribute</span></span>

<span data-ttu-id="9abe0-156">`Obsolete` 특성은 프로그램 엔터티를 더 이상 사용이 권장되지 않는 항목으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-156">The `Obsolete` attribute marks a program entity as one that is no longer recommended for use.</span></span> <span data-ttu-id="9abe0-157">나중에 사용되지 않음으로 표시된 엔터티를 사용할 때마다 특성 구성 방법에 따라 경고나 오류가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-157">Each use of an entity marked obsolete will subsequently generate a warning or an error, depending on how the attribute is configured.</span></span> <span data-ttu-id="9abe0-158">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-158">For example:</span></span>

```vb
<System.Obsolete("use class B")>
Class A
    Sub Method()
    End Sub
End Class

Class B
    <System.Obsolete("use NewMethod", True)>
    Sub OldMethod()
    End Sub

    Sub NewMethod()
    End Sub
End Class
```

<span data-ttu-id="9abe0-159">이 예제에서는 `Obsolete` 특성이 `A` 클래스 및 `B.OldMethod` 메서드에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-159">In this example the `Obsolete` attribute is applied to class `A` and to method `B.OldMethod`.</span></span> <span data-ttu-id="9abe0-160">`B.OldMethod`에 적용된 특성 생성자의 두 번째 인수가 `true`로 설정되므로 이 메서드는 컴파일러 오류를 일으키지만, `A` 클래스를 사용하면 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-160">Because the second argument of the attribute constructor applied to `B.OldMethod` is set to `true`, this method will cause a compiler error, whereas using class `A` will just produce a warning.</span></span> <span data-ttu-id="9abe0-161">그러나 `B.NewMethod`를 호출하면 경고나 오류가 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-161">Calling `B.NewMethod`, however, produces no warning or error.</span></span>

<span data-ttu-id="9abe0-162">특성 생성자에 첫 번째 인수로 제공된 문자열은 경고 또는 오류의 일부로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-162">The string provided as the first argument to attribute constructor will be displayed as part of the warning or error.</span></span> <span data-ttu-id="9abe0-163">예를 들어 이전 정의와 함께 사용할 경우 다음 코드에서는 두 개의 경고 및 하나의 오류가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-163">For example, when you use it with the previous definitions, the following code generates two warnings and one error:</span></span>

```vb
' Generates 2 warnings:
' Dim a As New A
' Generate no errors or warnings:

Dim b As New B
b.NewMethod()

' Generates an error, terminating compilation:
' b.OldMethod()
```

<span data-ttu-id="9abe0-164">`A` 클래스에 대한 두 개의 경고가 각각 클래스 참조 선언 및 클래스 생성자에 대해 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-164">Two warnings for class `A` are generated: one for the declaration of the class reference, and one for the class constructor.</span></span>

<span data-ttu-id="9abe0-165">`Obsolete` 특성은 인수 없이 사용할 수 있지만 항목이 사용되지 않는 이유와 대신 사용이 권장되는 항목에 대한 설명을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-165">The `Obsolete` attribute can be used without arguments, but including an explanation of why the item is obsolete and what to use instead is recommended.</span></span>

<span data-ttu-id="9abe0-166">`Obsolete` 특성은 단일 사용 특성이고 특성을 허용하는 모든 엔터티에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-166">The `Obsolete` attribute is a single-use attribute and can be applied to any entity that allows attributes.</span></span> <span data-ttu-id="9abe0-167">`Obsolete`는 <xref:System.ObsoleteAttribute>의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-167">`Obsolete` is an alias for <xref:System.ObsoleteAttribute>.</span></span>

## <a name="conditional-attribute"></a><a name="Conditional"></a><span data-ttu-id="9abe0-168">조건부 특성</span><span class="sxs-lookup"><span data-stu-id="9abe0-168">Conditional Attribute</span></span>

<span data-ttu-id="9abe0-169">`Conditional` 특성을 사용하면 메서드 실행이 전처리 식별자에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-169">The `Conditional` attribute makes the execution of a method dependent on a preprocessing identifier.</span></span> <span data-ttu-id="9abe0-170">`Conditional` 특성은 <xref:System.Diagnostics.ConditionalAttribute>의 별칭이고 메서드 또는 특성 클래스에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-170">The `Conditional` attribute is an alias for <xref:System.Diagnostics.ConditionalAttribute>, and can be applied to a method or an attribute class.</span></span>

<span data-ttu-id="9abe0-171">이 예제에서 `Conditional`은 프로그램 관련 진단 정보 표시를 사용하거나 사용하지 않도록 설정하는 메서드에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-171">In this example, `Conditional` is applied to a method to enable or disable the display of program-specific diagnostic information:</span></span>

```vb
#Const TRACE_ON = True
Imports System.Diagnostics

Module TestConditionalAttribute
    Public Class Trace
        <Conditional("TRACE_ON")>
        Public Shared Sub Msg(ByVal msg As String)
            Console.WriteLine(msg)
        End Sub

    End Class

    Sub Main()
        Trace.Msg("Now in Main...")
        Console.WriteLine("Done.")
    End Sub
End Module
```

<span data-ttu-id="9abe0-172">`TRACE_ON` 식별자가 정의되지 않으면 추적 출력이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-172">If the `TRACE_ON` identifier is not defined, no trace output will be displayed.</span></span>

<span data-ttu-id="9abe0-173">`Conditional` 특성은 보통 `DEBUG` 식별자와 함께 사용하여 다음과 같이 릴리스 빌드가 아닌 디버그 빌드의 추적 및 로깅 기능을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-173">The `Conditional` attribute is often used with the `DEBUG` identifier to enable trace and logging features for debug builds but not in release builds, like this:</span></span>

```vb
<Conditional("DEBUG")>
Shared Sub DebugMethod()

End Sub
```

<span data-ttu-id="9abe0-174">조건부로 표시된 메서드를 호출하면 지정된 전처리 기호가 있는지 여부에 따라 호출을 포함 또는 생략할지 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-174">When a method marked as conditional is called, the presence or absence of the specified preprocessing symbol determines whether the call is included or omitted.</span></span> <span data-ttu-id="9abe0-175">기호가 정의되면 호출이 포함되고, 정의되지 않으면 호출이 생략됩니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-175">If the symbol is defined, the call is included; otherwise, the call is omitted.</span></span> <span data-ttu-id="9abe0-176">다음과 같이 메서드를 `#if…#endif` 블록 내부에 포함하는 것보다 `Conditional`을 사용하는 것이 더 분명하고 더 정교하며 오류 가능성이 더 적습니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-176">Using `Conditional` is a cleaner, more elegant, and less error-prone alternative to enclosing methods inside `#if…#endif` blocks, like this:</span></span>

```vb
#If DEBUG Then
    Sub ConditionalMethod()
    End Sub
#End If
```

<span data-ttu-id="9abe0-177">조건부 메서드는 클래스 또는 구조체 선언의 메서드여야 하고 반환 값을 포함하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-177">A conditional method must be a method in a class or struct declaration and must not have a return value.</span></span>

### <a name="using-multiple-identifiers"></a><span data-ttu-id="9abe0-178">여러 식별자 사용</span><span class="sxs-lookup"><span data-stu-id="9abe0-178">Using Multiple Identifiers</span></span>

<span data-ttu-id="9abe0-179">한 메서드에 여러 `Conditional` 특성이 있을 경우 조건부 기호 중 하나 이상이 정의되면(즉, 기호가 OR 연산자를 통해 논리적으로 함께 연결되면) 메서드 호출이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-179">If a method has multiple `Conditional` attributes, a call to the method is included if at least one of the conditional symbols is defined (in other words, the symbols are logically linked together by using the OR operator).</span></span> <span data-ttu-id="9abe0-180">이 예제에서는 `A` 또는 `B`가 있으면 메서드 호출이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-180">In this example, the presence of either `A` or `B` will result in a method call:</span></span>

```vb
<Conditional("A"), Conditional("B")>
Shared Sub DoIfAorB()

End Sub
```

<span data-ttu-id="9abe0-181">AND 연산자를 통해 기호를 논리적으로 연결하는 결과를 얻으려면 순차적 조건부 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-181">To achieve the effect of logically linking symbols by using the AND operator, you can define serial conditional methods.</span></span> <span data-ttu-id="9abe0-182">예를 들어 아래 두 번째 메서드는 `A` 및 `B`가 둘 다 정의된 경우에만 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-182">For example, the second method below will execute only if both `A` and `B` are defined:</span></span>

```vb
<Conditional("A")>
Shared Sub DoIfA()
    DoIfAandB()
End Sub

<Conditional("B")>
Shared Sub DoIfAandB()
    ' Code to execute when both A and B are defined...
End Sub
```

### <a name="using-conditional-with-attribute-classes"></a><span data-ttu-id="9abe0-183">특성 클래스와 함께 조건부 사용</span><span class="sxs-lookup"><span data-stu-id="9abe0-183">Using Conditional with Attribute Classes</span></span>

<span data-ttu-id="9abe0-184">`Conditional` 특성을 특성 클래스 정의에 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-184">The `Conditional` attribute can also be applied to an attribute class definition.</span></span> <span data-ttu-id="9abe0-185">이 예제에서 사용자 지정 특성 `Documentation`은 DEBUG가 정의된 경우에만 메타데이터에 정보를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-185">In this example, the custom attribute `Documentation` will only add information to the metadata if DEBUG is defined.</span></span>

```vb
<Conditional("DEBUG")>
Public Class Documentation
    Inherits System.Attribute
    Private text As String
    Sub New(ByVal doc_text As String)
        text = doc_text
    End Sub
End Class

Class SampleClass
    ' This attribute will only be included if DEBUG is defined.
    <Documentation("This method displays an integer.")>
    Shared Sub DoWork(ByVal i As Integer)
        System.Console.WriteLine(i)
    End Sub
End Class
```

## <a name="caller-info-attributes"></a><a name="CallerInfo"></a><span data-ttu-id="9abe0-186">호출자 정보 특성</span><span class="sxs-lookup"><span data-stu-id="9abe0-186">Caller Info Attributes</span></span>

<span data-ttu-id="9abe0-187">호출자 정보 특성을 사용하여 메서드 호출자에 대한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-187">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="9abe0-188">소스 코드 파일 경로, 소스 코드 줄 번호 및 호출자의 멤버 이름을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-188">You can obtain the file path of the source code, the line number in the source code, and the member name of the caller.</span></span>

<span data-ttu-id="9abe0-189">멤버 호출자 정보를 얻으려면 선택적 매개 변수에 적용되는 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-189">To obtain member caller information, you use attributes that are applied to optional parameters.</span></span> <span data-ttu-id="9abe0-190">각 선택적 매개 변수는 기본값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-190">Each optional parameter specifies a default value.</span></span> <span data-ttu-id="9abe0-191">다음 표에서는 <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> 네임스페이스에 정의된 호출자 정보 특성을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-191">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace:</span></span>

|<span data-ttu-id="9abe0-192">특성</span><span class="sxs-lookup"><span data-stu-id="9abe0-192">Attribute</span></span>|<span data-ttu-id="9abe0-193">Description</span><span class="sxs-lookup"><span data-stu-id="9abe0-193">Description</span></span>|<span data-ttu-id="9abe0-194">형식</span><span class="sxs-lookup"><span data-stu-id="9abe0-194">Type</span></span>|
|---|---|---|
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|<span data-ttu-id="9abe0-195">호출자를 포함한 소스 파일의 전체 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-195">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="9abe0-196">컴파일 시간의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-196">This is the path at compile time.</span></span>|`String`|
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|<span data-ttu-id="9abe0-197">메서드가 호출되는 소스 파일의 줄 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-197">Line number in the source file from which the method is called.</span></span>|`Integer`|
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|<span data-ttu-id="9abe0-198">호출자의 메서드 이름 또는 속성 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-198">Method name or property name of the caller.</span></span> <span data-ttu-id="9abe0-199">자세한 내용은 [호출자 정보 (Visual Basic)](../caller-information.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9abe0-199">For more information, see [Caller Information (Visual Basic)](../caller-information.md).</span></span>|`String`|

<span data-ttu-id="9abe0-200">호출자 정보 특성에 대 한 자세한 내용은 [호출자 정보 (Visual Basic)](../caller-information.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9abe0-200">For more information about the Caller Info attributes, see [Caller Information (Visual Basic)](../caller-information.md).</span></span>

## <a name="visual-basic-attributes"></a><a name="VB"></a><span data-ttu-id="9abe0-201">Visual Basic 특성</span><span class="sxs-lookup"><span data-stu-id="9abe0-201">Visual Basic Attributes</span></span>

<span data-ttu-id="9abe0-202">다음 표에서는 Visual Basic 관련 된 특성을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-202">The following table lists the attributes that are specific to Visual Basic.</span></span>

|<span data-ttu-id="9abe0-203">특성</span><span class="sxs-lookup"><span data-stu-id="9abe0-203">Attribute</span></span>|<span data-ttu-id="9abe0-204">용도</span><span class="sxs-lookup"><span data-stu-id="9abe0-204">Purpose</span></span>|
|---------------|-------------|
|<xref:Microsoft.VisualBasic.ComClassAttribute>|<span data-ttu-id="9abe0-205">클래스가 COM 개체로 노출 되어야 함을 컴파일러에 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-205">Indicates to the compiler that the class should be exposed as a COM object.</span></span>|
|<xref:Microsoft.VisualBasic.HideModuleNameAttribute>|<span data-ttu-id="9abe0-206">모듈에 필요한 한정자만 사용 하 여 모듈 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-206">Allows module members to be accessed using only the qualification needed for the module.</span></span>|
|<xref:Microsoft.VisualBasic.VBFixedStringAttribute>|<span data-ttu-id="9abe0-207">파일 입력 및 출력 함수에 사용할 구조체의 고정 길이 문자열 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-207">Specifies the size of a fixed-length string in a structure for use with file input and output functions.</span></span>|
|<xref:Microsoft.VisualBasic.VBFixedArrayAttribute>|<span data-ttu-id="9abe0-208">파일 입력 및 출력 함수에 사용할 구조체의 고정 배열 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-208">Specifies the size of a fixed array in a structure for use with file input and output functions.</span></span>|

### <a name="comclassattribute"></a><span data-ttu-id="9abe0-209">M</span><span class="sxs-lookup"><span data-stu-id="9abe0-209">COMClassAttribute</span></span>

<span data-ttu-id="9abe0-210">`COMClassAttribute`를 사용 하 여 Visual Basic에서 COM 구성 요소를 만드는 프로세스를 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-210">Use `COMClassAttribute` to simplify the process of creating COM components from Visual Basic.</span></span> <span data-ttu-id="9abe0-211">COM 개체는 .NET Framework 어셈블리와 상당히 다르며, 없이는 `COMClassAttribute` 여러 단계를 수행 하 여 Visual Basic에서 com 개체를 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-211">COM objects are considerably different from .NET Framework assemblies, and without `COMClassAttribute`, you need to follow a number of steps to generate a COM object from Visual Basic.</span></span> <span data-ttu-id="9abe0-212">로 표시 된 클래스의 경우 `COMClassAttribute` 컴파일러는 이러한 단계를 자동으로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-212">For classes marked with `COMClassAttribute`, the compiler performs many of these steps automatically.</span></span>

### <a name="hidemodulenameattribute"></a><span data-ttu-id="9abe0-213">HideModuleNameAttribute</span><span class="sxs-lookup"><span data-stu-id="9abe0-213">HideModuleNameAttribute</span></span>

<span data-ttu-id="9abe0-214">`HideModuleNameAttribute`모듈에 필요한 한정자만 사용 하 여 모듈 멤버에 액세스할 수 있도록 하려면를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-214">Use `HideModuleNameAttribute` to allow module members to be accessed by using only the qualification needed for the module.</span></span>

### <a name="vbfixedstringattribute"></a><span data-ttu-id="9abe0-215">VBFixedStringAttribute</span><span class="sxs-lookup"><span data-stu-id="9abe0-215">VBFixedStringAttribute</span></span>

<span data-ttu-id="9abe0-216">`VBFixedStringAttribute`Visual Basic를 사용 하 여 고정 길이 문자열을 만들도록 강제 합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-216">Use `VBFixedStringAttribute` to force Visual Basic to create a fixed-length string.</span></span> <span data-ttu-id="9abe0-217">문자열은 기본적으로 가변 길이 이며이 특성은 파일에 문자열을 저장할 때 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-217">Strings are of variable length by default, and this attribute is useful when storing strings to files.</span></span> <span data-ttu-id="9abe0-218">다음 코드에서 이 과정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-218">The following code demonstrates this:</span></span>

```vb
Structure Worker
    ' The runtime uses VBFixedString to determine
    ' if the field should be written out as a fixed size.
    <VBFixedString(10)> Public LastName As String
    <VBFixedString(7)> Public Title As String
    <VBFixedString(2)> Public Rank As String
End Structure
```

### <a name="vbfixedarrayattribute"></a><span data-ttu-id="9abe0-219">VBFixedArrayAttribute</span><span class="sxs-lookup"><span data-stu-id="9abe0-219">VBFixedArrayAttribute</span></span>

<span data-ttu-id="9abe0-220">`VBFixedArrayAttribute`크기가 고정 된 배열을 선언 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-220">Use `VBFixedArrayAttribute` to declare arrays that are fixed in size.</span></span> <span data-ttu-id="9abe0-221">Visual Basic 문자열과 마찬가지로 배열은 기본적으로 가변 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-221">Like Visual Basic strings, arrays are of variable length by default.</span></span> <span data-ttu-id="9abe0-222">이 특성은 파일에 데이터를 직렬화 하거나 쓸 때 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9abe0-222">This attribute is useful when serializing or writing data to files.</span></span>

## <a name="see-also"></a><span data-ttu-id="9abe0-223">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9abe0-223">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="9abe0-224">Visual Basic 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="9abe0-224">Visual Basic Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="9abe0-225">특성</span><span class="sxs-lookup"><span data-stu-id="9abe0-225">Attributes</span></span>](../../../../standard/attributes/index.md)
- [<span data-ttu-id="9abe0-226">리플렉션(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9abe0-226">Reflection (Visual Basic)</span></span>](../reflection.md)
- [<span data-ttu-id="9abe0-227">리플렉션을 사용하여 특성 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9abe0-227">Accessing Attributes by Using Reflection (Visual Basic)</span></span>](accessing-attributes-by-using-reflection.md)
