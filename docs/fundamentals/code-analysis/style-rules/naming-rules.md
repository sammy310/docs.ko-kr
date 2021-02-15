---
title: 코드 스타일 명명 규칙
description: 코드 요소 명명에 대 한 .NET 코드 스타일 규칙에 대해 알아봅니다.
ms.date: 09/25/2020
ms.topic: reference
author: gewarren
ms.author: gewarren
dev_langs:
- CSharp
- VB
f1_keywords:
- IDE1006
- naming rules
helpviewer_keywords:
- IDE1006
- naming code style rules [EditorConfig]
- naming rules
- EditorConfig naming conventions
ms.openlocfilehash: df2cbc8299d853b5730bc39eb25c6f97b6575655
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429210"
---
# <a name="naming-rules"></a><span data-ttu-id="534c8-103">이름 지정 규칙</span><span class="sxs-lookup"><span data-stu-id="534c8-103">Naming rules</span></span>

<span data-ttu-id="534c8-104">파일에서 `.editorconfig` 클래스, 속성, 메서드 등의 .net 프로그래밍 언어 코드 요소 이름을 지정 하는 방법을 지정 하 고 적용 하는 **명명 규칙** 을 정의할 수 있습니다 &mdash; &mdash; .</span><span class="sxs-lookup"><span data-stu-id="534c8-104">In your `.editorconfig` file, you can define **naming rules** that specify and enforce how .NET programming language code elements&mdash;such as classes, properties, and methods&mdash;should be named.</span></span> <span data-ttu-id="534c8-105">예를 들어 public 멤버가 대문자로 표시 되거나 전용 필드가로 시작 되어야 하도록 지정할 수 있습니다 `_` .</span><span class="sxs-lookup"><span data-stu-id="534c8-105">For example, you can specify that public members must be capitalized, or that private fields must begin with `_`.</span></span>

<span data-ttu-id="534c8-106">명명 규칙에는 다음과 같은 세 가지 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-106">A naming rule has three components:</span></span>

* <span data-ttu-id="534c8-107">규칙이 적용 되는 **기호 그룹** (예: public 멤버 또는 전용 필드)입니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-107">The **symbol group** that the rule applies to, for example, public members or private fields.</span></span>
* <span data-ttu-id="534c8-108">규칙에 연결할 **명명 스타일** 입니다. 예를 들어 이름이 대문자로 또는 밑줄로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-108">The **naming style** to associate with the rule, for example, that the name must be capitalized or start with an underscore.</span></span>
* <span data-ttu-id="534c8-109">규칙 적용의 심각도입니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-109">The severity for enforcing the convention.</span></span>

<span data-ttu-id="534c8-110">먼저 기호 그룹 및 명명 스타일을 지정 하 고 각각에 제목을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-110">First, you must specify the symbol group and naming style and give each of them a title.</span></span> <span data-ttu-id="534c8-111">그런 다음 모든 항목을 연결 하는 명명 규칙을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-111">Then you specify the naming rule, which links everything together.</span></span>

## <a name="general-syntax"></a><span data-ttu-id="534c8-112">일반 구문</span><span class="sxs-lookup"><span data-stu-id="534c8-112">General syntax</span></span>

<span data-ttu-id="534c8-113">명명 규칙, 기호 그룹 또는 명명 스타일을 정의 하려면 다음 구문을 사용 하 여 하나 이상의 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-113">To define a naming rule, symbol group, or naming style, set one or more properties using the following syntax:</span></span>

```ini
<kind>.<title>.<propertyName> = <propertyValue>
```

<span data-ttu-id="534c8-114">각 속성은 한 번만 설정 해야 하지만 일부 설정에서는 쉼표로 구분 된 여러 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-114">Each property should only be set once, but some settings allow multiple, comma-separated values.</span></span>

<span data-ttu-id="534c8-115">속성의 순서는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-115">The order of the properties is not important.</span></span>

### \<kind>

<span data-ttu-id="534c8-116">**\<kind>** 정의 되는 &mdash; 명명 규칙, 기호 그룹 또는 명명 스타일의 요소 종류를 지정 &mdash; 하 고 다음 중 하나 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-116">**\<kind>** specifies which kind of element is being defined&mdash;naming rule, symbol group, or naming style&mdash;and must be one of the following:</span></span>

| <span data-ttu-id="534c8-117">속성을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="534c8-117">To set a property for</span></span> | <span data-ttu-id="534c8-118">값 사용 \<kind></span><span class="sxs-lookup"><span data-stu-id="534c8-118">Use the \<kind> value</span></span> | <span data-ttu-id="534c8-119">예</span><span class="sxs-lookup"><span data-stu-id="534c8-119">Example</span></span> |
| --- | --- | -- |
| <span data-ttu-id="534c8-120">명명 규칙</span><span class="sxs-lookup"><span data-stu-id="534c8-120">Naming rule</span></span> | `dotnet_naming_rule` | `dotnet_naming_rule.types_should_be_pascal_case.severity = suggestion` |
| <span data-ttu-id="534c8-121">기호 그룹</span><span class="sxs-lookup"><span data-stu-id="534c8-121">Symbol group</span></span> | `dotnet_naming_symbols` | `dotnet_naming_symbols.interface.applicable_kinds = interface` |
| <span data-ttu-id="534c8-122">명명 스타일</span><span class="sxs-lookup"><span data-stu-id="534c8-122">Naming style</span></span> | `dotnet_naming_style` | `dotnet_naming_style.pascal_case.capitalization = pascal_case` |

<span data-ttu-id="534c8-123">&mdash;다음 섹션에 설명 된 대로 각 유형의 정의[명명 규칙](#naming-rule-properties), [기호 그룹](#symbol-group-properties)또는 [명명 스타일](#naming-style-properties) &mdash; 에는 고유한 지원 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-123">Each type of definition&mdash;[naming rule](#naming-rule-properties), [symbol group](#symbol-group-properties), or [naming style](#naming-style-properties)&mdash;has its own supported properties, as described in the following sections.</span></span>

### \<title>

<span data-ttu-id="534c8-124">**\<title>** 는 여러 속성 설정을 단일 정의로 연결 하는 설명이 포함 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-124">**\<title>** is a descriptive name you choose that associates multiple property settings into a single definition.</span></span> <span data-ttu-id="534c8-125">예를 들어, 다음 속성은 두 개의 기호 그룹 정의를 생성 하 `interface` 고 `types` 각각에 두 개의 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-125">For example, the following properties produce two symbol group definitions, `interface` and `types`, each of which has two properties set on it.</span></span>

```ini
dotnet_naming_symbols.interface.applicable_kinds = interface
dotnet_naming_symbols.interface.applicable_accessibilities = public, internal, private, protected, protected_internal, private_protected

dotnet_naming_symbols.types.applicable_kinds = class, struct, interface, enum, delegate
dotnet_naming_symbols.types.applicable_accessibilities = public, internal, private, protected, protected_internal, private_protected
```

## <a name="naming-rule-properties"></a><span data-ttu-id="534c8-126">명명 규칙 속성</span><span class="sxs-lookup"><span data-stu-id="534c8-126">Naming rule properties</span></span>

<span data-ttu-id="534c8-127">규칙이 적용 되려면 모든 명명 규칙 속성이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-127">All naming rule properties are required for a rule to take effect.</span></span>

| <span data-ttu-id="534c8-128">속성</span><span class="sxs-lookup"><span data-stu-id="534c8-128">Property</span></span> | <span data-ttu-id="534c8-129">설명</span><span class="sxs-lookup"><span data-stu-id="534c8-129">Description</span></span> |
| -- | -- |
| `symbols` | <span data-ttu-id="534c8-130">기호 그룹의 제목입니다. 명명 규칙은이 그룹의 기호에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-130">The title of a symbol group; the naming rule will be applied to the symbols in this group</span></span> |
| `style` | <span data-ttu-id="534c8-131">이 규칙과 연결 되어야 하는 명명 스타일의 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-131">The title of the naming style which should be associated with this rule</span></span> |
| `severity` |  <span data-ttu-id="534c8-132">명명 규칙을 적용 하는 데 사용 되는 심각도를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-132">Sets the severity with which to enforce the naming rule.</span></span> <span data-ttu-id="534c8-133">연결 된 값을 사용 가능한 [심각도 수준](../configuration-options.md#severity-level)중 하나로 설정 합니다. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="534c8-133">Set the associated value to one of the available [severity levels](../configuration-options.md#severity-level).<sup>1</sup></span></span> |

<span data-ttu-id="534c8-134">**참고:**</span><span class="sxs-lookup"><span data-stu-id="534c8-134">**Notes:**</span></span>

1. <span data-ttu-id="534c8-135">명명 규칙 내의 심각도 사양은 Visual Studio와 같은 개발 Ide 내 에서만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-135">Severity specification within a naming rule is only respected inside development IDEs, such as Visual Studio.</span></span> <span data-ttu-id="534c8-136">이 설정은 c # 또는 VB 컴파일러에서 인식 되지 않으므로 빌드하는 동안에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-136">This setting is not understood by the C# or VB compilers, hence not respected during build.</span></span> <span data-ttu-id="534c8-137">빌드에 명명 스타일 규칙을 적용 하려면 [코드 규칙 심각도 구성을](#rule-id-ide1006-naming-rule-violation)사용 하 여 심각도를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-137">To enforce naming style rules on build, you should instead set the severity by using [code rule severity configuration](#rule-id-ide1006-naming-rule-violation).</span></span> <span data-ttu-id="534c8-138">자세한 내용은 이 [GitHub 문제](https://github.com/dotnet/roslyn/issues/44201)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="534c8-138">For more information, see this [GitHub issue](https://github.com/dotnet/roslyn/issues/44201).</span></span>

## <a name="symbol-group-properties"></a><span data-ttu-id="534c8-139">기호 그룹 속성</span><span class="sxs-lookup"><span data-stu-id="534c8-139">Symbol group properties</span></span>

<span data-ttu-id="534c8-140">기호 그룹에 대해 다음 속성을 설정 하 여 그룹에 포함 되는 기호를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-140">You can set the following properties for symbol groups, to limit which symbols are included in the group.</span></span> <span data-ttu-id="534c8-141">단일 속성에 대해 여러 값을 지정 하려면 값을 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-141">To specify multiple values for a single property, separate the values with a comma.</span></span>

| <span data-ttu-id="534c8-142">속성</span><span class="sxs-lookup"><span data-stu-id="534c8-142">Property</span></span> | <span data-ttu-id="534c8-143">Description</span><span class="sxs-lookup"><span data-stu-id="534c8-143">Description</span></span> | <span data-ttu-id="534c8-144">허용되는 값</span><span class="sxs-lookup"><span data-stu-id="534c8-144">Allowed values</span></span> | <span data-ttu-id="534c8-145">필수</span><span class="sxs-lookup"><span data-stu-id="534c8-145">Required</span></span> |
| -- | -- | -- | -- |
| `applicable_kinds` | <span data-ttu-id="534c8-146">그룹 1의 기호 종류 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="534c8-146">Kinds of symbols in the group <sup>1</sup></span></span> | <span data-ttu-id="534c8-147">`*`(모든 기호를 지정하려면 이 값을 사용합니다.)</span><span class="sxs-lookup"><span data-stu-id="534c8-147">`*` (use this value to specify all symbols)</span></span><br/>`namespace`<br/>`class`<br/>`struct`<br/>`interface`<br/>`enum`<br/>`property`<br/>`method`<br/>`field`<br/>`event`<br/>`delegate`<br/>`parameter`<br/>`type_parameter`<br/>`local`<br/>`local_function` | <span data-ttu-id="534c8-148">Yes</span><span class="sxs-lookup"><span data-stu-id="534c8-148">Yes</span></span> |
| `applicable_accessibilities` | <span data-ttu-id="534c8-149">그룹에 있는 기호의 액세스 가능성 수준</span><span class="sxs-lookup"><span data-stu-id="534c8-149">Accessibility levels of the symbols in the group</span></span> | <span data-ttu-id="534c8-150">`*`(모든 액세스 가능성 수준을 지정하려면 이 값을 사용합니다.)</span><span class="sxs-lookup"><span data-stu-id="534c8-150">`*` (use this value to specify all accessibility levels)</span></span><br/>`public`<br/><span data-ttu-id="534c8-151">`internal` 또는 `friend`</span><span class="sxs-lookup"><span data-stu-id="534c8-151">`internal` or `friend`</span></span><br/>`private`<br/>`protected`<br/><span data-ttu-id="534c8-152">`protected_internal` 또는 `protected_friend`</span><span class="sxs-lookup"><span data-stu-id="534c8-152">`protected_internal` or `protected_friend`</span></span><br/>`private_protected`<br/><span data-ttu-id="534c8-153">`local` (메서드 내에 정의 된 기호의 경우)</span><span class="sxs-lookup"><span data-stu-id="534c8-153">`local` (for symbols defined within a method)</span></span> | <span data-ttu-id="534c8-154">Yes</span><span class="sxs-lookup"><span data-stu-id="534c8-154">Yes</span></span> |
| `required_modifiers` | <span data-ttu-id="534c8-155">지정 된 한정자 <sup>2</sup> 를 _모두_ 사용 하는 기호만 일치</span><span class="sxs-lookup"><span data-stu-id="534c8-155">Only match symbols with _all_ the specified modifiers <sup>2</sup></span></span> | <span data-ttu-id="534c8-156">`abstract` 또는 `must_inherit`</span><span class="sxs-lookup"><span data-stu-id="534c8-156">`abstract` or `must_inherit`</span></span><br/>`async`<br/>`const`<br/>`readonly`<br/><span data-ttu-id="534c8-157">`static` 또는 `shared` <sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="534c8-157">`static` or `shared` <sup>3</sup></span></span> | <span data-ttu-id="534c8-158">예</span><span class="sxs-lookup"><span data-stu-id="534c8-158">No</span></span> |

<span data-ttu-id="534c8-159">**참고:**</span><span class="sxs-lookup"><span data-stu-id="534c8-159">**Notes:**</span></span>

1. <span data-ttu-id="534c8-160">튜플 멤버는 현재에서 지원 되지 않습니다 `applicable_kinds` .</span><span class="sxs-lookup"><span data-stu-id="534c8-160">Tuple members aren't currently supported in `applicable_kinds`.</span></span>
2. <span data-ttu-id="534c8-161">기호 그룹은 속성의 _모든_ 한정자와 일치 합니다 `required_modifiers` .</span><span class="sxs-lookup"><span data-stu-id="534c8-161">The symbol group matches _all_ the modifiers in the `required_modifiers` property.</span></span>  <span data-ttu-id="534c8-162">이 속성을 생략 하면 일치에 특정 한정자가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-162">If you omit this property, no specific modifiers are required for a match.</span></span> <span data-ttu-id="534c8-163">즉, 기호 한정자가 이 규칙의 적용 여부에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-163">This means a symbol's modifiers have no effect on whether or not this rule is applied.</span></span>
3. <span data-ttu-id="534c8-164">그룹에 `static` 또는 속성이 있는 경우 `shared` `required_modifiers` 그룹은 `const` 암시적 이기 때문에 기호도 포함 합니다 `static` / `Shared` .</span><span class="sxs-lookup"><span data-stu-id="534c8-164">If your group has `static` or `shared` in the `required_modifiers` property, the group will also include `const` symbols because they are implicitly `static`/`Shared`.</span></span> <span data-ttu-id="534c8-165">그러나 `static` 명명 규칙을 기호에 적용 하지 않으려면 `const` 의 기호 그룹을 사용 하 여 새 명명 규칙을 만들 수 있습니다 `const` .</span><span class="sxs-lookup"><span data-stu-id="534c8-165">However, if you don't want the `static` naming rule to apply to `const` symbols, you can create a new naming rule with a symbol group of `const`.</span></span>

## <a name="naming-style-properties"></a><span data-ttu-id="534c8-166">이름 지정 스타일 속성</span><span class="sxs-lookup"><span data-stu-id="534c8-166">Naming style properties</span></span>

<span data-ttu-id="534c8-167">명명 스타일은 규칙을 사용 하 여 적용 하려는 규칙을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-167">A naming style defines the conventions you want to enforce with the rule.</span></span> <span data-ttu-id="534c8-168">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-168">For example:</span></span>

* <span data-ttu-id="534c8-169">다음으로 대문자화 `PascalCase`</span><span class="sxs-lookup"><span data-stu-id="534c8-169">Capitalize with `PascalCase`</span></span>
* <span data-ttu-id="534c8-170">시작 문자 `m_`</span><span class="sxs-lookup"><span data-stu-id="534c8-170">Starts with `m_`</span></span>
* <span data-ttu-id="534c8-171">끝 문자 `_g`</span><span class="sxs-lookup"><span data-stu-id="534c8-171">Ends with `_g`</span></span>
* <span data-ttu-id="534c8-172">단어 구분 `__`</span><span class="sxs-lookup"><span data-stu-id="534c8-172">Separate words with `__`</span></span>

<span data-ttu-id="534c8-173">명명 스타일에 대해 다음 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-173">You can set the following properties for a naming style:</span></span>

| <span data-ttu-id="534c8-174">속성</span><span class="sxs-lookup"><span data-stu-id="534c8-174">Property</span></span> | <span data-ttu-id="534c8-175">Description</span><span class="sxs-lookup"><span data-stu-id="534c8-175">Description</span></span> | <span data-ttu-id="534c8-176">허용되는 값</span><span class="sxs-lookup"><span data-stu-id="534c8-176">Allowed values</span></span> | <span data-ttu-id="534c8-177">필수</span><span class="sxs-lookup"><span data-stu-id="534c8-177">Required</span></span> |
| -- | -- | -- | -- |
| `capitalization` | <span data-ttu-id="534c8-178">기호 내의 단어에 대 한 대/소문자 스타일</span><span class="sxs-lookup"><span data-stu-id="534c8-178">Capitalization style for words within the symbol</span></span> | `pascal_case`<br/>`camel_case`<br/>`first_word_upper`<br/>`all_upper`<br/>`all_lower` | <span data-ttu-id="534c8-179">예<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="534c8-179">Yes<sup>1</sup></span></span> |
| `required_prefix` | <span data-ttu-id="534c8-180">다음 문자로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-180">Must begin with these characters</span></span> | | <span data-ttu-id="534c8-181">예</span><span class="sxs-lookup"><span data-stu-id="534c8-181">No</span></span> |
| `required_suffix` | <span data-ttu-id="534c8-182">다음 문자로 끝나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-182">Must end with these characters</span></span> | | <span data-ttu-id="534c8-183">예</span><span class="sxs-lookup"><span data-stu-id="534c8-183">No</span></span> |
| `word_separator` | <span data-ttu-id="534c8-184">기호 내의 단어는이 문자로 구분 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-184">Words within the symbol need to be separated with this character</span></span> | | <span data-ttu-id="534c8-185">예</span><span class="sxs-lookup"><span data-stu-id="534c8-185">No</span></span> |

<span data-ttu-id="534c8-186">**참고:**</span><span class="sxs-lookup"><span data-stu-id="534c8-186">**Notes:**</span></span>

1. <span data-ttu-id="534c8-187">명명 스타일의 일부로 대/소문자 스타일을 지정해야 하고, 그렇지 않으면 명명 스타일이 무시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-187">You must specify a capitalization style as part of your naming style, otherwise your naming style might be ignored.</span></span>

## <a name="rule-order"></a><span data-ttu-id="534c8-188">규칙 순서</span><span class="sxs-lookup"><span data-stu-id="534c8-188">Rule order</span></span>

<span data-ttu-id="534c8-189">EditorConfig 파일에 명명 규칙을 정의 하는 순서는 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-189">The order in which naming rules are defined in an EditorConfig file doesn't matter.</span></span> <span data-ttu-id="534c8-190">명명 규칙은 규칙 자체의 정의에 따라 자동으로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-190">The naming rules are automatically ordered according to the definition of the rules themselves.</span></span> <span data-ttu-id="534c8-191">[EditorConfig 언어 서비스 확장](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig)은 EditorConfig 파일을 분석하고, 파일의 규칙 순서가 런타임에 컴파일러에서 사용할 순서와 다른 경우를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-191">The [EditorConfig Language Service extension](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.EditorConfig) can analyze an EditorConfig file and report cases where the rule ordering in the file is different to what the compiler will use at run time.</span></span>

> [!NOTE]
>
> <span data-ttu-id="534c8-192">Visual Studio 2019 버전 16.2 보다 이전 버전의 Visual Studio를 사용 하는 경우 명명 규칙은 EditorConfig 파일에서 가장 특정에서 최소 전용으로 정렬 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-192">If you're using a version of Visual Studio earlier than Visual Studio 2019 version 16.2, naming rules should be ordered from most-specific to least-specific in the EditorConfig file.</span></span> <span data-ttu-id="534c8-193">적용할 수 있는 첫 번째 규칙은 적용되는 유일한 규칙이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-193">The first rule encountered that can be applied is the only rule that is applied.</span></span> <span data-ttu-id="534c8-194">그러나 동일한 이름의 규칙 ‘속성’이 여러 개 있는 경우 가장 최근에 발견된 해당 이름의 속성이 우선 적용됩니다. </span><span class="sxs-lookup"><span data-stu-id="534c8-194">However, if there are multiple rule *properties* with the same name, the most recently found property with that name takes precedence.</span></span> <span data-ttu-id="534c8-195">자세한 내용은 [파일 계층 구조 및 우선 순위](/visualstudio/ide/create-portable-custom-editor-options#file-hierarchy-and-precedence)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="534c8-195">For more information, see [File hierarchy and precedence](/visualstudio/ide/create-portable-custom-editor-options#file-hierarchy-and-precedence).</span></span>

## <a name="default-naming-styles"></a><span data-ttu-id="534c8-196">기본 명명 스타일</span><span class="sxs-lookup"><span data-stu-id="534c8-196">Default naming styles</span></span>

<span data-ttu-id="534c8-197">사용자 지정 명명 규칙을 지정 하지 않으면 다음 기본 스타일이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-197">If you don't specify any custom naming rules, the following default styles are used:</span></span>

- <span data-ttu-id="534c8-198">`public`, `private`, `internal`, `protected` 또는 `protected_internal` 접근성이 있는 클래스, 구조체, 열거형, 속성, 이벤트의 기본 명명 스타일은 파스칼식 대/소문자입니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-198">For classes, structs, enumerations, properties, and events with `public`, `private`, `internal`, `protected`, or `protected_internal` accessibility, the default naming style is Pascal case.</span></span>

- <span data-ttu-id="534c8-199">`public`, `private`, `internal`, `protected` 또는 `protected_internal` 접근성이 있는 인터페이스의 기본 명명 스타일은 필수 접두사 **I** 를 사용하는 파스칼식 대/소문자입니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-199">For interfaces with `public`, `private`, `internal`, `protected`, or `protected_internal` accessibility, the default naming style is Pascal case with a required prefix of **I**.</span></span>

## <a name="code-rule-id-ide1006-naming-rule-violation"></a><a name="rule-id-ide1006-naming-rule-violation"></a><span data-ttu-id="534c8-200">코드 규칙 ID: `IDE1006 (Naming rule violation)`</span><span class="sxs-lookup"><span data-stu-id="534c8-200">Code Rule ID: `IDE1006 (Naming rule violation)`</span></span>

<span data-ttu-id="534c8-201">모든 이름 지정 옵션에는 규칙 ID `IDE1006` 와 제목이 있습니다 `Naming rule violation` .</span><span class="sxs-lookup"><span data-stu-id="534c8-201">All naming options have rule ID `IDE1006` and title `Naming rule violation`.</span></span> <span data-ttu-id="534c8-202">다음 구문을 사용 하 여 EditorConfig 파일에서 전역적으로 명명 위반의 심각도를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-202">You can configure the severity of naming violations globally in an EditorConfig file with the following syntax:</span></span>

```ini
dotnet_diagnostic.IDE1006.severity = <severity value>
```

<span data-ttu-id="534c8-203">심각도 값은 `warning` `error` [빌드 시 적용](../overview.md#code-style-analysis)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-203">The severity value must be `warning` or `error` to be [enforced on build](../overview.md#code-style-analysis).</span></span> <span data-ttu-id="534c8-204">가능한 모든 심각도 값은 [심각도 수준](../configuration-options.md#severity-level)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="534c8-204">For all possible severity values, see [severity level](../configuration-options.md#severity-level).</span></span>

## <a name="example"></a><span data-ttu-id="534c8-205">예제</span><span class="sxs-lookup"><span data-stu-id="534c8-205">Example</span></span>

<span data-ttu-id="534c8-206">다음 *.editorconfig* 파일은 공용 속성, 메서드, 필드, 이벤트 및 대리자를 대문자로 시작하도록 지정하는 명명 규칙을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-206">The following *.editorconfig* file contains a naming convention that specifies that public properties, methods, fields, events, and delegates must be capitalized.</span></span> <span data-ttu-id="534c8-207">이 명명 규칙은 값을 구분하기 위해 쉼표를 사용하여 규칙을 적용하는 여러 종류의 기호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="534c8-207">Notice that this naming convention specifies multiple kinds of symbol to apply the rule to, using a comma to separate the values.</span></span>

```ini
[*.{cs,vb}]

# Defining the 'public_symbols' symbol group
dotnet_naming_symbols.public_symbols.applicable_kinds           = property,method,field,event,delegate
dotnet_naming_symbols.public_symbols.applicable_accessibilities = public
dotnet_naming_symbols.public_symbols.required_modifiers         = readonly

# Defining the `first_word_upper_case_style` naming style
dotnet_naming_style.first_word_upper_case_style.capitalization = first_word_upper

# Defining the `public_members_must_be_capitalized` naming rule, by setting the symbol group to the 'public symbols' symbol group,
dotnet_naming_rule.public_members_must_be_capitalized.symbols   = public_symbols
# setting the naming style to the `first_word_upper_case_style` naming style,
dotnet_naming_rule.public_members_must_be_capitalized.style    = first_word_upper_case_style
# and setting the severity.
dotnet_naming_rule.public_members_must_be_capitalized.severity = suggestion
```

## <a name="see-also"></a><span data-ttu-id="534c8-208">추가 정보</span><span class="sxs-lookup"><span data-stu-id="534c8-208">See also</span></span>

- [<span data-ttu-id="534c8-209">언어 규칙</span><span class="sxs-lookup"><span data-stu-id="534c8-209">Language rules</span></span>](language-rules.md)
- [<span data-ttu-id="534c8-210">서식 지정 규칙</span><span class="sxs-lookup"><span data-stu-id="534c8-210">Formatting rules</span></span>](formatting-rules.md)
- [<span data-ttu-id="534c8-211">Roslyn 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="534c8-211">Roslyn naming rules</span></span>](https://github.com/dotnet/roslyn/blob/master/.editorconfig#L63)
- [<span data-ttu-id="534c8-212">.NET 코드 스타일 규칙 참조</span><span class="sxs-lookup"><span data-stu-id="534c8-212">.NET code style rules reference</span></span>](index.md)
