---
title: 정규화된 형식 이름 지정
ms.date: 02/21/2019
helpviewer_keywords:
- names [.NET Framework], fully qualified type names
- reflection, fully qualified type names
- names [.NET Framework], assemblies
- tokens
- BNF
- assemblies [.NET Framework], names
- languages, grammar
- fully qualified type names
- type names
- special characters
- IDENTIFIER
ms.assetid: d90b1e39-9115-4f2a-81c0-05e7e74e5580
ms.openlocfilehash: 707c71482196d789ed9a88db34af048ec57734fb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130029"
---
# <a name="specifying-fully-qualified-type-names"></a><span data-ttu-id="3659a-102">정규화된 형식 이름 지정</span><span class="sxs-lookup"><span data-stu-id="3659a-102">Specifying fully qualified type names</span></span>

<span data-ttu-id="3659a-103">다양한 리플렉션 작업에 대한 유효한 입력을 포함하려면 형식 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-103">You must specify type names to have valid input to various reflection operations.</span></span> <span data-ttu-id="3659a-104">정규화된 형식 이름은 어셈블리 이름 사양, 네임스페이스 사양, 형식 이름으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-104">A fully qualified type name consists of an assembly name specification, a namespace specification, and a type name.</span></span> <span data-ttu-id="3659a-105">형식 이름 사양은 <xref:System.Type.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> 등의 메서드에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-105">Type name specifications are used by methods such as <xref:System.Type.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>, and <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>.</span></span>

## <a name="grammar-for-type-names"></a><span data-ttu-id="3659a-106">형식 이름의 문법</span><span class="sxs-lookup"><span data-stu-id="3659a-106">Grammar for type names</span></span>

 <span data-ttu-id="3659a-107">문법은 공식 언어의 구문을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-107">The grammar defines the syntax of formal languages.</span></span> <span data-ttu-id="3659a-108">다음 표에서는 유효한 입력을 인식하는 방법을 설명하는 어휘 규칙을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-108">The following table lists lexical rules that describe how to recognize a valid input.</span></span> <span data-ttu-id="3659a-109">터미널(더 이상 줄일 수 없는 요소)은 모두 대문자로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-109">Terminals (those elements that are not further reducible) are shown in all uppercase letters.</span></span> <span data-ttu-id="3659a-110">비터미널(더 줄일 수 있는 요소)은 대/소문자가 혼합되어 있거나 작은따옴표가 붙은 문자열로 표시되지만 작은따옴표(')는 구문 자체에 속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-110">Nonterminals (those elements that are further reducible) are shown in mixed-case or singly quoted strings, but the single quote (') is not a part of the syntax itself.</span></span> <span data-ttu-id="3659a-111">파이프 문자(&#124;)는 하위 규칙이 있는 규칙을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-111">The pipe character (&#124;) denotes rules that have subrules.</span></span>

<!-- markdownlint-disable MD010 -->
```antlr
TypeSpec
    : ReferenceTypeSpec
    | SimpleTypeSpec
    ;

ReferenceTypeSpec
    : SimpleTypeSpec '&'
    ;

SimpleTypeSpec
    : PointerTypeSpec
    | GenericTypeSpec
    | TypeName
    ;

GenericTypeSpec
   : SimpleTypeSpec ` NUMBER

PointerTypeSpec
    : SimpleTypeSpec '*'
    ;

ArrayTypeSpec
    : SimpleTypeSpec '[ReflectionDimension]'
    | SimpleTypeSpec '[ReflectionEmitDimension]'
    ;

ReflectionDimension
    : '*'
    | ReflectionDimension ',' ReflectionDimension
    | NOTOKEN
    ;

ReflectionEmitDimension
    : '*'
    | Number '..' Number
    | Number '…'
    | ReflectionDimension ',' ReflectionDimension
    | NOTOKEN
    ;

Number
    : [0-9]+
    ;

TypeName
    : NamespaceTypeName
    | NamespaceTypeName ',' AssemblyNameSpec
    ;

NamespaceTypeName
    : NestedTypeName
    | NamespaceSpec '.' NestedTypeName
    ;

NestedTypeName
    : IDENTIFIER
    | NestedTypeName '+' IDENTIFIER
    ;

NamespaceSpec
    : IDENTIFIER
    | NamespaceSpec '.' IDENTIFIER
    ;

AssemblyNameSpec
    : IDENTIFIER
    | IDENTIFIER ',' AssemblyProperties
    ;

AssemblyProperties
    : AssemblyProperty
    | AssemblyProperties ',' AssemblyProperty
    ;

AssemblyProperty
    : AssemblyPropertyName '=' AssemblyPropertyValue
    ;
```
<!-- markdownlint-enable MD010 -->

## <a name="specifying-special-characters"></a><span data-ttu-id="3659a-112">특수 문자 지정</span><span class="sxs-lookup"><span data-stu-id="3659a-112">Specifying special characters</span></span>

<span data-ttu-id="3659a-113">형식 이름에서 IDENTIFIER는 언어의 규칙에 따라 결정된 유효한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-113">In a type name, IDENTIFIER is any valid name determined by the rules of a language.</span></span>

<span data-ttu-id="3659a-114">백슬래시(\\)를 이스케이프 문자로 사용하여 IDENTIFIER의 일부로 사용된 다음 토큰을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-114">Use the backslash (\\) as an escape character to separate the following tokens when used as part of IDENTIFIER.</span></span>

|<span data-ttu-id="3659a-115">토큰</span><span class="sxs-lookup"><span data-stu-id="3659a-115">Token</span></span>|<span data-ttu-id="3659a-116">의미</span><span class="sxs-lookup"><span data-stu-id="3659a-116">Meaning</span></span>|
|-----------|-------------|
|<span data-ttu-id="3659a-117">\\,</span><span class="sxs-lookup"><span data-stu-id="3659a-117">\\,</span></span>|<span data-ttu-id="3659a-118">어셈블리 구분 기호.</span><span class="sxs-lookup"><span data-stu-id="3659a-118">Assembly separator.</span></span>|
|\\+|<span data-ttu-id="3659a-119">중첩된 형식 구분 기호.</span><span class="sxs-lookup"><span data-stu-id="3659a-119">Nested type separator.</span></span>|
|\\&|<span data-ttu-id="3659a-120">참조 형식.</span><span class="sxs-lookup"><span data-stu-id="3659a-120">Reference type.</span></span>|
|\\*|<span data-ttu-id="3659a-121">포인터 형식.</span><span class="sxs-lookup"><span data-stu-id="3659a-121">Pointer type.</span></span>|
|<span data-ttu-id="3659a-122">\\[</span><span class="sxs-lookup"><span data-stu-id="3659a-122">\\[</span></span>|<span data-ttu-id="3659a-123">배열 차원 구분 기호.</span><span class="sxs-lookup"><span data-stu-id="3659a-123">Array dimension delimiter.</span></span>|
|<span data-ttu-id="3659a-124">\\]</span><span class="sxs-lookup"><span data-stu-id="3659a-124">\\]</span></span>|<span data-ttu-id="3659a-125">배열 차원 구분 기호.</span><span class="sxs-lookup"><span data-stu-id="3659a-125">Array dimension delimiter.</span></span>|
|<span data-ttu-id="3659a-126">\\</span><span class="sxs-lookup"><span data-stu-id="3659a-126">\\.</span></span>|<span data-ttu-id="3659a-127">배열 사양에서 마침표가 사용된 경우에만 마침표 앞에 백슬래시를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-127">Use the backslash before a period only if the period is used in an array specification.</span></span> <span data-ttu-id="3659a-128">NamespaceSpec의 마침표는 백슬래시를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-128">Periods in NamespaceSpec do not take the backslash.</span></span>|
|<span data-ttu-id="3659a-129">\\\|필요한 경우 백슬래시를 문자열 리터럴로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-129">\\\|Backslash when needed as a string literal.</span></span>|

<span data-ttu-id="3659a-130">AssemblyNameSpec을 제외한 모든 TypeSpec 구성 요소에서 공백은 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-130">Note that in all TypeSpec components except AssemblyNameSpec, spaces are relevant.</span></span> <span data-ttu-id="3659a-131">AssemblyNameSpec에서는 ',' 구분 기호 앞의 공백은 관련이 있지만 ',' 구분 기호 뒤의 공백은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-131">In the AssemblyNameSpec, spaces before the ',' separator are relevant, but spaces after the ',' separator are ignored.</span></span>

<span data-ttu-id="3659a-132"><xref:System.Type.FullName%2A?displayProperty=nameWithType> 등의 리플렉션 클래스는 `MyType.GetType(myType.FullName)`과 같이 반환된 이름을 <xref:System.Type.GetType%2A> 호출에 사용할 수 있도록 바뀐 이름을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-132">Reflection classes, such as <xref:System.Type.FullName%2A?displayProperty=nameWithType>, return the mangled name so that the returned name can be used in a call to <xref:System.Type.GetType%2A>, as in `MyType.GetType(myType.FullName)`.</span></span>

<span data-ttu-id="3659a-133">예를 들어 형식의 정규화된 이름이 `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-133">For example, the fully qualified name for a type might be `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly`.</span></span>

<span data-ttu-id="3659a-134">네임스페이스가 `Ozzy.Out+Back`이면 더하기 기호 앞에 백슬래시가 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-134">If the namespace were `Ozzy.Out+Back`, then the plus sign must be preceded by a backslash.</span></span> <span data-ttu-id="3659a-135">그렇지 않으면 파서가 중첩 구분 기호로 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-135">Otherwise, the parser would interpret it as a nesting separator.</span></span> <span data-ttu-id="3659a-136">리플렉션은 이 문자열을 `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly`로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-136">Reflection emits this string as `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly`.</span></span>

## <a name="specifying-assembly-names"></a><span data-ttu-id="3659a-137">어셈블리 이름 지정</span><span class="sxs-lookup"><span data-stu-id="3659a-137">Specifying assembly names</span></span>

<span data-ttu-id="3659a-138">어셈블리 이름 사양에 필요한 최소 정보는 어셈블리의 텍스트 이름(IDENTIFIER)입니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-138">The minimum information required in an assembly name specification is the textual name (IDENTIFIER) of the assembly.</span></span> <span data-ttu-id="3659a-139">다음 표에 설명된 대로 속성/값 쌍의 쉼표로 구분된 목록이 IDENTIFIER 뒤에 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-139">You can follow the IDENTIFIER by a comma-separated list of property/value pairs as described in the following table.</span></span> <span data-ttu-id="3659a-140">IDENTIFIER 이름 지정은 파일 이름 지정 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-140">IDENTIFIER naming should follow the rules for file naming.</span></span> <span data-ttu-id="3659a-141">IDENTIFIER는 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-141">The IDENTIFIER is case-insensitive.</span></span>

|<span data-ttu-id="3659a-142">속성 이름</span><span class="sxs-lookup"><span data-stu-id="3659a-142">Property name</span></span>|<span data-ttu-id="3659a-143">설명</span><span class="sxs-lookup"><span data-stu-id="3659a-143">Description</span></span>|<span data-ttu-id="3659a-144">허용 가능한 값</span><span class="sxs-lookup"><span data-stu-id="3659a-144">Allowable values</span></span>|
|-------------------|-----------------|----------------------|
|<span data-ttu-id="3659a-145">**Version**</span><span class="sxs-lookup"><span data-stu-id="3659a-145">**Version**</span></span>|<span data-ttu-id="3659a-146">어셈블리 버전 번호</span><span class="sxs-lookup"><span data-stu-id="3659a-146">Assembly version number</span></span>|<span data-ttu-id="3659a-147">*Major.Minor.Build.Revision*. 여기서 *Major*, *Minor*, *Build*, *Revision*은 0에서 65535 사이의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-147">*Major.Minor.Build.Revision*, where *Major*, *Minor*, *Build*, and *Revision* are integers between 0 and 65535 inclusive.</span></span>|
|<span data-ttu-id="3659a-148">**PublicKey**</span><span class="sxs-lookup"><span data-stu-id="3659a-148">**PublicKey**</span></span>|<span data-ttu-id="3659a-149">전체 공개 키</span><span class="sxs-lookup"><span data-stu-id="3659a-149">Full public key</span></span>|<span data-ttu-id="3659a-150">16진수 형식인 전체 공개 키의 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-150">String value of full public key in hexadecimal format.</span></span> <span data-ttu-id="3659a-151">null 참조(Visual Basic에서는 **Nothing**)를 지정하여 프라이빗 어셈블리를 명시적으로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-151">Specify a null reference (**Nothing** in Visual Basic) to explicitly indicate a private assembly.</span></span>|
|<span data-ttu-id="3659a-152">**PublicKeyToken**</span><span class="sxs-lookup"><span data-stu-id="3659a-152">**PublicKeyToken**</span></span>|<span data-ttu-id="3659a-153">공개 키 토큰(전체 공개 키의 8바이트 해시)</span><span class="sxs-lookup"><span data-stu-id="3659a-153">Public key token (8-byte hash of the full public key)</span></span>|<span data-ttu-id="3659a-154">16진수 형식인 공개 키 토큰의 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-154">String value of public key token in hexadecimal format.</span></span> <span data-ttu-id="3659a-155">null 참조(Visual Basic에서는 **Nothing**)를 지정하여 프라이빗 어셈블리를 명시적으로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-155">Specify a null reference (**Nothing** in Visual Basic) to explicitly indicate a private assembly.</span></span>|
|<span data-ttu-id="3659a-156">**문화권**.</span><span class="sxs-lookup"><span data-stu-id="3659a-156">**Culture**</span></span>|<span data-ttu-id="3659a-157">어셈블리 문화권</span><span class="sxs-lookup"><span data-stu-id="3659a-157">Assembly culture</span></span>|<span data-ttu-id="3659a-158">RFC-1766 형식의 어셈블리 문화권 또는 언어 독립적인(비위성) 어셈블리의 경우 "중립"입니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-158">Culture of the assembly in RFC-1766 format, or "neutral" for language-independent (nonsatellite) assemblies.</span></span>|
|<span data-ttu-id="3659a-159">**사용자 지정**</span><span class="sxs-lookup"><span data-stu-id="3659a-159">**Custom**</span></span>|<span data-ttu-id="3659a-160">사용자 지정 BLOB(Binary Large Object)입니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-160">Custom binary large object (BLOB).</span></span> <span data-ttu-id="3659a-161">현재 [네이티브 이미지 생성기(Ngen)](../tools/ngen-exe-native-image-generator.md)에서 생성된 어셈블리에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-161">This is currently used only in assemblies generated by the [Native Image Generator (Ngen)](../tools/ngen-exe-native-image-generator.md).</span></span>|<span data-ttu-id="3659a-162">설치되는 어셈블리가 네이티브 이미지이므로 네이티브 이미지 캐시에 설치해야 함을 어셈블리 캐시에 알리기 위해 네이티브 이미지 생성기 도구에서 사용하는 사용자 지정 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-162">Custom string used by the Native Image Generator tool to notify the assembly cache that the assembly being installed is a native image, and is therefore to be installed in the native image cache.</span></span> <span data-ttu-id="3659a-163">zap 문자열이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-163">Also called a zap string.</span></span>|

<span data-ttu-id="3659a-164">다음 예제에서는 기본 문화권을 사용하는 단순한 이름의 어셈블리에 대한 **AssemblyName**을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-164">The following example shows an **AssemblyName** for a simply named assembly with default culture.</span></span>

```csharp
com.microsoft.crypto, Culture=""
```

<span data-ttu-id="3659a-165">다음 예제에서는 문화권 "en"을 사용하는 강력한 이름의 어셈블리에 대한 완전히 지정된 참조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-165">The following example shows a fully specified reference for a strongly named assembly with culture "en".</span></span>

```csharp
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,
    Version=1.0.0.0
```

<span data-ttu-id="3659a-166">다음 예제에서는 각각 강력한 이름 또는 단순한 이름의 어셈블리에 의해 충족될 수 있는 부분적으로 지정된 **AssemblyName**을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-166">The following examples each show a partially specified **AssemblyName**, which can be satisfied by either a strong or a simply named assembly.</span></span>

```csharp
com.microsoft.crypto
com.microsoft.crypto, Culture=""
com.microsoft.crypto, Culture=en
```

<span data-ttu-id="3659a-167">다음 예제에서는 각각 단순한 이름의 어셈블리에 의해 충족되어야 하는 부분적으로 지정된 **AssemblyName**을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-167">The following examples each show a partially specified **AssemblyName**, which must be satisfied by a simply named assembly.</span></span>

```csharp
com.microsoft.crypto, Culture="", PublicKeyToken=null
com.microsoft.crypto, Culture=en, PublicKeyToken=null
```

<span data-ttu-id="3659a-168">다음 예제에서는 각각 강력한 이름의 어셈블리에 의해 충족되어야 하는 부분적으로 지정된 **AssemblyName**을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-168">The following examples each show a partially specified **AssemblyName**, which must be satisfied by a strongly named assembly.</span></span>

```csharp
com.microsoft.crypto, Culture="", PublicKeyToken=a5d015c7d5a0b012
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,
    Version=1.0.0.0
```

## <a name="specifying-generic-types"></a><span data-ttu-id="3659a-169">제네릭 형식 지정</span><span class="sxs-lookup"><span data-stu-id="3659a-169">Specifying generic types</span></span>

<span data-ttu-id="3659a-170">SimpleTypeSpec\`NUMBER는 1부터 *n*까지의 제네릭 형식 매개 변수를 갖는 개방형 제네릭 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-170">SimpleTypeSpec\`NUMBER represents an open generic type with from 1 to *n* generic type parameters.</span></span> <span data-ttu-id="3659a-171">예를 들어, 개방형 제네릭 형식 List\<T> 또는 폐쇄형 제네릭 형식 List\<String>의 참조를 가져오려면 ``Type.GetType("System.Collections.Generic.List`1")``을 사용합니다. 제네릭 형식 Dictionary\<TKey,TValue>의 참조를 가져오려면 ``Type.GetType("System.Collections.Generic.Dictionary`2")``를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-171">For example, to get reference to the open generic type List\<T> or the closed generic type List\<String>, use ``Type.GetType("System.Collections.Generic.List`1")`` To get a reference to the generic type Dictionary\<TKey,TValue>, use ``Type.GetType("System.Collections.Generic.Dictionary`2")``.</span></span>

## <a name="specifying-pointers"></a><span data-ttu-id="3659a-172">포인터 지정</span><span class="sxs-lookup"><span data-stu-id="3659a-172">Specifying pointers</span></span>

<span data-ttu-id="3659a-173">SimpleTypeSpec\*는 관리되지 않는 포인터를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-173">SimpleTypeSpec\* represents an unmanaged pointer.</span></span> <span data-ttu-id="3659a-174">예를 들어 MyType 형식에 대한 포인터를 가져오려면 `Type.GetType("MyType*")`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-174">For example, to get a pointer to type MyType, use `Type.GetType("MyType*")`.</span></span> <span data-ttu-id="3659a-175">MyType 형식에 대한 포인터의 포인터를 가져오려면 `Type.GetType("MyType**")`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-175">To get a pointer to a pointer to type MyType, use `Type.GetType("MyType**")`.</span></span>

## <a name="specifying-references"></a><span data-ttu-id="3659a-176">참조 지정</span><span class="sxs-lookup"><span data-stu-id="3659a-176">Specifying references</span></span>

<span data-ttu-id="3659a-177">SimpleTypeSpec &은 관리되는 포인터나 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-177">SimpleTypeSpec & represents a managed pointer or reference.</span></span> <span data-ttu-id="3659a-178">예를 들어 MyType 형식에 대한 참조를 가져오려면 `Type.GetType("MyType &")`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-178">For example, to get a reference to type MyType, use `Type.GetType("MyType &")`.</span></span> <span data-ttu-id="3659a-179">포인터와 달리 참조는 한 수준으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-179">Note that unlike pointers, references are limited to one level.</span></span>

## <a name="specifying-arrays"></a><span data-ttu-id="3659a-180">배열 지정</span><span class="sxs-lookup"><span data-stu-id="3659a-180">Specifying arrays</span></span>

<span data-ttu-id="3659a-181">BNF 문법에서 ReflectionEmitDimension은 <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>을 사용하여 검색된 불완전한 형식 정의에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-181">In the BNF Grammar, ReflectionEmitDimension only applies to incomplete type definitions retrieved using <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3659a-182">불완전한 형식 정의는 <xref:System.Reflection.Emit?displayProperty=nameWithType>을 사용하여 생성되었지만 <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=nameWithType>이 호출되지 않은 <xref:System.Reflection.Emit.TypeBuilder> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-182">Incomplete type definitions are <xref:System.Reflection.Emit.TypeBuilder> objects constructed using <xref:System.Reflection.Emit?displayProperty=nameWithType> but on which <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=nameWithType> has not been called.</span></span> <span data-ttu-id="3659a-183">ReflectionDimension을 사용하여 완성된 형식 정의, 즉 로드된 형식을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-183">ReflectionDimension can be used to retrieve any type definition that has been completed, that is, a type that has been loaded.</span></span>

<span data-ttu-id="3659a-184">배열은 배열의 순위를 지정하여 리플렉션에서 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-184">Arrays are accessed in reflection by specifying the rank of the array:</span></span>

- <span data-ttu-id="3659a-185">`Type.GetType("MyArray[]")`은 하한이 0인 1차원 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-185">`Type.GetType("MyArray[]")` gets a single-dimension array with 0 lower bound.</span></span>

- <span data-ttu-id="3659a-186">`Type.GetType("MyArray[*]")`은 하한을 알 수 없는 1차원 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-186">`Type.GetType("MyArray[*]")` gets a single-dimension array with unknown lower bound.</span></span>
- <span data-ttu-id="3659a-187">`Type.GetType("MyArray[][]")`은 2차원 배열의 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-187">`Type.GetType("MyArray[][]")` gets a two-dimensional array's array.</span></span>

- <span data-ttu-id="3659a-188">`Type.GetType("MyArray[*,*]")` 및 `Type.GetType("MyArray[,]")`은 하한을 알 수 없는 사각형 2차원 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-188">`Type.GetType("MyArray[*,*]")` and `Type.GetType("MyArray[,]")` gets a rectangular two-dimensional array with unknown lower bounds.</span></span>

<span data-ttu-id="3659a-189">런타임 관점에서는 `MyArray[] != MyArray[*]`이지만, 다차원 배열에서는 두 표기법이 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-189">Note that from a runtime point of view, `MyArray[] != MyArray[*]`, but for multidimensional arrays, the two notations are equivalent.</span></span> <span data-ttu-id="3659a-190">즉, `Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")`은 **true**입니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-190">That is, `Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` evaluates to **true**.</span></span>

<span data-ttu-id="3659a-191">**ModuleBuilder.GetType**의 경우 `MyArray[0..5]`는 크기가 6, 하한이 0인 1차원 배열을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-191">For **ModuleBuilder.GetType**, `MyArray[0..5]` indicates a single-dimension array with size 6, lower bound 0.</span></span> <span data-ttu-id="3659a-192">`MyArray[4…]`는 크기를 알 수 없고 하한이 4인 1차원 배열을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3659a-192">`MyArray[4…]` indicates a single-dimension array of unknown size and lower bound 4.</span></span>

## <a name="see-also"></a><span data-ttu-id="3659a-193">참조</span><span class="sxs-lookup"><span data-stu-id="3659a-193">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- <xref:System.Reflection.Emit.ModuleBuilder>
- <xref:System.Reflection.Emit.TypeBuilder>
- <xref:System.Type.FullName%2A?displayProperty=nameWithType>
- <xref:System.Type.GetType%2A?displayProperty=nameWithType>
- <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType>
- [<span data-ttu-id="3659a-194">형식 정보 보기</span><span class="sxs-lookup"><span data-stu-id="3659a-194">Viewing Type Information</span></span>](viewing-type-information.md)
