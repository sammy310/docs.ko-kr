---
title: 코드 스타일 언어 규칙
description: 'C # 및 Visual Basic 언어 구문을 사용 하기 위한 다양 한 코드 스타일 규칙에 대해 알아봅니다.'
ms.date: 09/25/2020
ms.topic: reference
author: gewarren
ms.author: gewarren
dev_langs:
- CSharp
- VB
helpviewer_keywords:
- language code style rules [EditorConfig]
- language rules
- EditorConfig language conventions
ms.openlocfilehash: b77d9aa2a528a6cf540babd5e5acc148e48c489c
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96594165"
---
# <a name="language-rules"></a><span data-ttu-id="02bd4-103">언어 규칙</span><span class="sxs-lookup"><span data-stu-id="02bd4-103">Language rules</span></span>

<span data-ttu-id="02bd4-104">코드 스타일 언어 규칙은 한정자 및 괄호와 같은 .NET 프로그래밍 언어의 다양 한 구문이 사용 되는 방식에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="02bd4-104">Code style language rules affect how various constructs of .NET programming languages, for example, modifiers and parentheses, are used.</span></span> <span data-ttu-id="02bd4-105">규칙은 다음과 같은 범주로 분류 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02bd4-105">The rules fall into the following categories:</span></span>

- <span data-ttu-id="02bd4-106">[.Net 스타일 규칙](#net-style-rules): c # 및 Visual Basic 모두에 적용 되는 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="02bd4-106">[.NET style rules](#net-style-rules): Rules that apply to both C# and Visual Basic.</span></span> <span data-ttu-id="02bd4-107">이러한 규칙에 대 한 EditorConfig 옵션 이름은 접두사로 시작 합니다 `dotnet_style_` .</span><span class="sxs-lookup"><span data-stu-id="02bd4-107">The EditorConfig option names for these rules start with `dotnet_style_` prefix.</span></span>
- <span data-ttu-id="02bd4-108">[C # 스타일 규칙](#c-style-rules): c # 언어에만 적용 되는 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="02bd4-108">[C# style rules](#c-style-rules): Rules that are specific to C# language only.</span></span> <span data-ttu-id="02bd4-109">이러한 규칙에 대 한 EditorConfig 옵션 이름은 접두사로 시작 합니다 `csharp_style_` .</span><span class="sxs-lookup"><span data-stu-id="02bd4-109">The EditorConfig option names for these rules start with `csharp_style_` prefix.</span></span>
- <span data-ttu-id="02bd4-110">[Visual Basic 스타일 규칙](#visual-basic-style-rules): Visual Bsic language에만 적용 되는 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="02bd4-110">[Visual Basic style rules](#visual-basic-style-rules): Rules that are specific to Visual Bsic language only.</span></span> <span data-ttu-id="02bd4-111">이러한 규칙에 대 한 EditorConfig 옵션 이름은 접두사로 시작 합니다 `visual_basic_style_` .</span><span class="sxs-lookup"><span data-stu-id="02bd4-111">The EditorConfig option names for these rules start with `visual_basic_style_` prefix.</span></span>

## <a name="option-format"></a><span data-ttu-id="02bd4-112">옵션 형식</span><span class="sxs-lookup"><span data-stu-id="02bd4-112">Option format</span></span>

<span data-ttu-id="02bd4-113">언어 규칙에 대 한 옵션은 다음과 같은 형식의 EditorConfig 파일에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02bd4-113">Options for language rules can be specified in an EditorConfig file with the following format:</span></span>

`option_name = value:severity`

- <span data-ttu-id="02bd4-114">**값**: 각 언어 규칙에 대해 스타일을 선호 하는지 여부를 정의 하는 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="02bd4-114">**Value**: For each language rule, you specify a value that defines if or when to prefer the style.</span></span> <span data-ttu-id="02bd4-115">대부분의 규칙은 `true`(이 스타일 선호) 또는 `false`(이 스타일 선호 안 함) 값을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="02bd4-115">Many rules accept a value of `true` (prefer this style) or `false` (do not prefer this style).</span></span> <span data-ttu-id="02bd4-116">다른 규칙은 `when_on_single_line`, `never` 등의 값을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="02bd4-116">Other rules accept values such as `when_on_single_line` or `never`.</span></span>
- <span data-ttu-id="02bd4-117">**심각도**: 규칙의 두 번째 부분은 규칙의 [심각도 수준을](../configuration-options.md#severity-level) 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="02bd4-117">**Severity**: The second part of the rule specifies the [severity level](../configuration-options.md#severity-level) for the rule.</span></span> <span data-ttu-id="02bd4-118">심각도 사양은 위 옵션 구문의 일부로 Visual Studio와 같은 개발 Ide 내 에서만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02bd4-118">Severity specification as part of the above option syntax is only respected inside development IDEs, such as Visual Studio.</span></span> <span data-ttu-id="02bd4-119">이 설정은 c # 또는 VB 컴파일러에서 인식 되지 않으므로 빌드하는 동안에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02bd4-119">This setting is not understood by the C# or VB compilers, hence not respected during build.</span></span> <span data-ttu-id="02bd4-120">대신 코드 스타일 규칙을 빌드에 적용 하려면 분석기에 대 한 규칙 ID 기반 심각도 구성 구문을 사용 하 여 심각도를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02bd4-120">Instead, to enforce code style rules on build, you should set the severity by using the rule ID-based severity configuration syntax for analyzers.</span></span> <span data-ttu-id="02bd4-121">구문은 `dotnet_diagnostic.<rule ID>.severity = <severity>` 형식을 사용합니다(예: `dotnet_diagnostic.IDE0040.severity = silent`).</span><span class="sxs-lookup"><span data-stu-id="02bd4-121">The syntax takes the form `dotnet_diagnostic.<rule ID>.severity = <severity>`, for example, `dotnet_diagnostic.IDE0040.severity = silent`.</span></span> <span data-ttu-id="02bd4-122">자세한 내용은 이 [GitHub 문제](https://github.com/dotnet/roslyn/issues/44201)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02bd4-122">For more information, see this [GitHub issue](https://github.com/dotnet/roslyn/issues/44201).</span></span>

> [!TIP]
>
> <span data-ttu-id="02bd4-123">Visual Studio 2019 버전 16.3부터, 스타일 위반이 발생한 후에 [빠른 작업](/visualstudio/ide/quick-actions) 전구 메뉴에서 코드 스타일 규칙을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02bd4-123">Starting in Visual Studio 2019 version 16.3, you can configure code style rules from the [Quick Actions](/visualstudio/ide/quick-actions) light bulb menu after a style violation occurs.</span></span> <span data-ttu-id="02bd4-124">자세한 내용은 [Visual Studio에서 자동으로 코드 스타일 구성](/visualstudio/ide/editorconfig-language-conventions#automatically-configure-code-styles-in-visual-studio)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="02bd4-124">For more information, see [Automatically configure code styles in Visual Studio](/visualstudio/ide/editorconfig-language-conventions#automatically-configure-code-styles-in-visual-studio).</span></span>

## <a name="net-style-rules"></a><span data-ttu-id="02bd4-125">.NET 스타일 규칙</span><span class="sxs-lookup"><span data-stu-id="02bd4-125">.NET style rules</span></span>

<span data-ttu-id="02bd4-126">이 섹션의 스타일 규칙은 C# 및 Visual Basic 모두에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="02bd4-126">The style rules in this section are applicable to both C# and Visual Basic.</span></span>

- [<span data-ttu-id="02bd4-127">' this. ' 및 ' Me. ' 한정자</span><span class="sxs-lookup"><span data-stu-id="02bd4-127">'this.' and 'Me.' qualifiers</span></span>](ide0003-ide0009.md)
  - [<span data-ttu-id="02bd4-128">dotnet_style_qualification_for_field</span><span class="sxs-lookup"><span data-stu-id="02bd4-128">dotnet_style_qualification_for_field</span></span>](ide0003-ide0009.md#dotnet_style_qualification_for_field)
  - [<span data-ttu-id="02bd4-129">dotnet_style_qualification_for_property</span><span class="sxs-lookup"><span data-stu-id="02bd4-129">dotnet_style_qualification_for_property</span></span>](ide0003-ide0009.md#dotnet_style_qualification_for_property)
  - [<span data-ttu-id="02bd4-130">dotnet_style_qualification_for_method</span><span class="sxs-lookup"><span data-stu-id="02bd4-130">dotnet_style_qualification_for_method</span></span>](ide0003-ide0009.md#dotnet_style_qualification_for_method)
  - [<span data-ttu-id="02bd4-131">dotnet_style_qualification_for_event</span><span class="sxs-lookup"><span data-stu-id="02bd4-131">dotnet_style_qualification_for_event</span></span>](ide0003-ide0009.md#dotnet_style_qualification_for_event)
- [<span data-ttu-id="02bd4-132">형식 참조를 위한 프레임워크 형식 이름 대신 언어 키워드</span><span class="sxs-lookup"><span data-stu-id="02bd4-132">Language keywords instead of framework type names for type references</span></span>](ide0049.md)
  - [<span data-ttu-id="02bd4-133">dotnet_style_predefined_type_for_locals_parameters_members</span><span class="sxs-lookup"><span data-stu-id="02bd4-133">dotnet_style_predefined_type_for_locals_parameters_members</span></span>](ide0049.md#dotnet_style_predefined_type_for_locals_parameters_members)
  - [<span data-ttu-id="02bd4-134">dotnet_style_predefined_type_for_member_access</span><span class="sxs-lookup"><span data-stu-id="02bd4-134">dotnet_style_predefined_type_for_member_access</span></span>](ide0049.md#dotnet_style_predefined_type_for_member_access)
- [<span data-ttu-id="02bd4-135">한정자 기본 설정</span><span class="sxs-lookup"><span data-stu-id="02bd4-135">Modifier preferences</span></span>](modifier-preferences.md#net-modifier-preferences)
  - [<span data-ttu-id="02bd4-136">dotnet_style_require_accessibility_modifiers</span><span class="sxs-lookup"><span data-stu-id="02bd4-136">dotnet_style_require_accessibility_modifiers</span></span>](ide0040.md#dotnet_style_require_accessibility_modifiers)
  - [<span data-ttu-id="02bd4-137">csharp_preferred_modifier_order</span><span class="sxs-lookup"><span data-stu-id="02bd4-137">csharp_preferred_modifier_order</span></span>](ide0036.md#csharp_preferred_modifier_order)
  - [<span data-ttu-id="02bd4-138">visual_basic_preferred_modifier_order</span><span class="sxs-lookup"><span data-stu-id="02bd4-138">visual_basic_preferred_modifier_order</span></span>](ide0036.md#visual_basic_preferred_modifier_order)
  - [<span data-ttu-id="02bd4-139">dotnet_style_readonly_field</span><span class="sxs-lookup"><span data-stu-id="02bd4-139">dotnet_style_readonly_field</span></span>](ide0044.md#dotnet_style_readonly_field)
- [<span data-ttu-id="02bd4-140">괄호 기본 설정</span><span class="sxs-lookup"><span data-stu-id="02bd4-140">Parentheses preferences</span></span>](ide0047-ide0048.md)
  - [<span data-ttu-id="02bd4-141">dotnet_style_parentheses_in_arithmetic_binary_operators</span><span class="sxs-lookup"><span data-stu-id="02bd4-141">dotnet_style_parentheses_in_arithmetic_binary_operators</span></span>](ide0047-ide0048.md#dotnet_style_parentheses_in_arithmetic_binary_operators)
  - [<span data-ttu-id="02bd4-142">dotnet_style_parentheses_in_relational_binary_operators</span><span class="sxs-lookup"><span data-stu-id="02bd4-142">dotnet_style_parentheses_in_relational_binary_operators</span></span>](ide0047-ide0048.md#dotnet_style_parentheses_in_relational_binary_operators)
  - [<span data-ttu-id="02bd4-143">dotnet_style_parentheses_in_other_binary_operators</span><span class="sxs-lookup"><span data-stu-id="02bd4-143">dotnet_style_parentheses_in_other_binary_operators</span></span>](ide0047-ide0048.md#dotnet_style_parentheses_in_other_binary_operators)
  - [<span data-ttu-id="02bd4-144">dotnet_style_parentheses_in_other_operators</span><span class="sxs-lookup"><span data-stu-id="02bd4-144">dotnet_style_parentheses_in_other_operators</span></span>](ide0047-ide0048.md#dotnet_style_parentheses_in_other_operators)
- [<span data-ttu-id="02bd4-145">식 수준 기본 설정</span><span class="sxs-lookup"><span data-stu-id="02bd4-145">Expression-level preferences</span></span>](expression-level-preferences.md#net-expression-level-preferences)
  - [<span data-ttu-id="02bd4-146">dotnet_style_object_initializer</span><span class="sxs-lookup"><span data-stu-id="02bd4-146">dotnet_style_object_initializer</span></span>](ide0017.md#dotnet_style_object_initializer)
  - [<span data-ttu-id="02bd4-147">dotnet_style_collection_initializer</span><span class="sxs-lookup"><span data-stu-id="02bd4-147">dotnet_style_collection_initializer</span></span>](ide0028.md#dotnet_style_collection_initializer)
  - [<span data-ttu-id="02bd4-148">dotnet_style_explicit_tuple_names</span><span class="sxs-lookup"><span data-stu-id="02bd4-148">dotnet_style_explicit_tuple_names</span></span>](ide0033.md#dotnet_style_explicit_tuple_names)
  - [<span data-ttu-id="02bd4-149">dotnet_style_prefer_inferred_tuple_names</span><span class="sxs-lookup"><span data-stu-id="02bd4-149">dotnet_style_prefer_inferred_tuple_names</span></span>](ide0037.md#dotnet_style_prefer_inferred_tuple_names)
  - [<span data-ttu-id="02bd4-150">dotnet_style_prefer_inferred_anonymous_type_member_names</span><span class="sxs-lookup"><span data-stu-id="02bd4-150">dotnet_style_prefer_inferred_anonymous_type_member_names</span></span>](ide0037.md#dotnet_style_prefer_inferred_anonymous_type_member_names)
  - [<span data-ttu-id="02bd4-151">dotnet_style_prefer_auto_properties</span><span class="sxs-lookup"><span data-stu-id="02bd4-151">dotnet_style_prefer_auto_properties</span></span>](ide0032.md#dotnet_style_prefer_auto_properties)
  - [<span data-ttu-id="02bd4-152">dotnet_style_prefer_conditional_expression_over_assignment</span><span class="sxs-lookup"><span data-stu-id="02bd4-152">dotnet_style_prefer_conditional_expression_over_assignment</span></span>](ide0045.md#dotnet_style_prefer_conditional_expression_over_assignment)
  - [<span data-ttu-id="02bd4-153">dotnet_style_prefer_conditional_expression_over_return</span><span class="sxs-lookup"><span data-stu-id="02bd4-153">dotnet_style_prefer_conditional_expression_over_return</span></span>](ide0046.md#dotnet_style_prefer_conditional_expression_over_return)
  - [<span data-ttu-id="02bd4-154">dotnet_style_prefer_compound_assignment</span><span class="sxs-lookup"><span data-stu-id="02bd4-154">dotnet_style_prefer_compound_assignment</span></span>](ide0054-ide0074.md#dotnet_style_prefer_compound_assignment)
  - [<span data-ttu-id="02bd4-155">dotnet_style_prefer_simplified_interpolation</span><span class="sxs-lookup"><span data-stu-id="02bd4-155">dotnet_style_prefer_simplified_interpolation</span></span>](ide0071.md#dotnet_style_prefer_simplified_interpolation)
  - [<span data-ttu-id="02bd4-156">dotnet_style_prefer_simplified_boolean_expressions</span><span class="sxs-lookup"><span data-stu-id="02bd4-156">dotnet_style_prefer_simplified_boolean_expressions</span></span>](ide0075.md#dotnet_style_prefer_simplified_boolean_expressions)
  - <span data-ttu-id="02bd4-157">[Switch 문에 누락 된 사례 추가](ide0010.md) -이 규칙에는 코드 스타일 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02bd4-157">[Add missing cases to switch statement](ide0010.md) - This rule has no code style option.</span></span>
  - <span data-ttu-id="02bd4-158">[무명 형식을 튜플로 변환](ide0050.md) -이 규칙에는 코드 스타일 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02bd4-158">[Convert anonymous type to tuple](ide0050.md) - This rule has no code style option.</span></span>
  - <span data-ttu-id="02bd4-159">[' 해시 코드 '를 사용](ide0070.md) 합니다 .이 규칙에는 코드 스타일 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02bd4-159">[Use 'System.HashCode.Combine'](ide0070.md) - This rule has no code style option.</span></span>
  - <span data-ttu-id="02bd4-160">[' Typeof '를 ' nameof '로 변환](ide0082.md) -이 규칙에는 코드 스타일 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02bd4-160">[Convert 'typeof' to 'nameof'](ide0082.md) - This rule has no code style option.</span></span>
- [<span data-ttu-id="02bd4-161">Null 검사 기본 설정</span><span class="sxs-lookup"><span data-stu-id="02bd4-161">Null-checking preferences</span></span>](null-checking-preferences.md#net-null-checking-preferences)
  - [<span data-ttu-id="02bd4-162">dotnet_style_coalesce_expression</span><span class="sxs-lookup"><span data-stu-id="02bd4-162">dotnet_style_coalesce_expression</span></span>](ide0029-ide0030.md#dotnet_style_coalesce_expression)
  - [<span data-ttu-id="02bd4-163">dotnet_style_null_propagation</span><span class="sxs-lookup"><span data-stu-id="02bd4-163">dotnet_style_null_propagation</span></span>](ide0031.md#dotnet_style_null_propagation)
  - [<span data-ttu-id="02bd4-164">dotnet_style_prefer_is_null_check_over_reference_equality_method</span><span class="sxs-lookup"><span data-stu-id="02bd4-164">dotnet_style_prefer_is_null_check_over_reference_equality_method</span></span>](ide0041.md#dotnet_style_prefer_is_null_check_over_reference_equality_method)
- [<span data-ttu-id="02bd4-165">파일 헤더 기본 설정</span><span class="sxs-lookup"><span data-stu-id="02bd4-165">File header preferences</span></span>](ide0073.md)
  - [<span data-ttu-id="02bd4-166">file_header_template</span><span class="sxs-lookup"><span data-stu-id="02bd4-166">file_header_template</span></span>](ide0073.md#file_header_template)

## <a name="c-style-rules"></a><span data-ttu-id="02bd4-167">C # 스타일 규칙</span><span class="sxs-lookup"><span data-stu-id="02bd4-167">C# style rules</span></span>

<span data-ttu-id="02bd4-168">이 섹션의 스타일 규칙은 c # 언어에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02bd4-168">The style rules in this section are applicable to C# language only.</span></span>

- [<span data-ttu-id="02bd4-169">' var ' 기본 설정</span><span class="sxs-lookup"><span data-stu-id="02bd4-169">'var' preferences</span></span>](ide0007-ide0008.md)
  - [<span data-ttu-id="02bd4-170">csharp_style_var_for_built_in_types</span><span class="sxs-lookup"><span data-stu-id="02bd4-170">csharp_style_var_for_built_in_types</span></span>](ide0007-ide0008.md#csharp_style_var_for_built_in_types)
  - [<span data-ttu-id="02bd4-171">csharp_style_var_when_type_is_apparent</span><span class="sxs-lookup"><span data-stu-id="02bd4-171">csharp_style_var_when_type_is_apparent</span></span>](ide0007-ide0008.md#csharp_style_var_when_type_is_apparent)
  - [<span data-ttu-id="02bd4-172">csharp_style_var_elsewhere</span><span class="sxs-lookup"><span data-stu-id="02bd4-172">csharp_style_var_elsewhere</span></span>](ide0007-ide0008.md#csharp_style_var_elsewhere)
- [<span data-ttu-id="02bd4-173">식 본문 멤버</span><span class="sxs-lookup"><span data-stu-id="02bd4-173">Expression-bodied members</span></span>](expression-bodied-members.md)
  - [<span data-ttu-id="02bd4-174">csharp_style_expression_bodied_methods</span><span class="sxs-lookup"><span data-stu-id="02bd4-174">csharp_style_expression_bodied_methods</span></span>](ide0022.md#csharp_style_expression_bodied_methods)
  - [<span data-ttu-id="02bd4-175">csharp_style_expression_bodied_constructors</span><span class="sxs-lookup"><span data-stu-id="02bd4-175">csharp_style_expression_bodied_constructors</span></span>](ide0021.md#csharp_style_expression_bodied_constructors)
  - [<span data-ttu-id="02bd4-176">csharp_style_expression_bodied_operators</span><span class="sxs-lookup"><span data-stu-id="02bd4-176">csharp_style_expression_bodied_operators</span></span>](ide0023-ide0024.md#csharp_style_expression_bodied_operators)
  - [<span data-ttu-id="02bd4-177">csharp_style_expression_bodied_properties</span><span class="sxs-lookup"><span data-stu-id="02bd4-177">csharp_style_expression_bodied_properties</span></span>](ide0025.md#csharp_style_expression_bodied_properties)
  - [<span data-ttu-id="02bd4-178">csharp_style_expression_bodied_indexers</span><span class="sxs-lookup"><span data-stu-id="02bd4-178">csharp_style_expression_bodied_indexers</span></span>](ide0026.md#csharp_style_expression_bodied_indexers)
  - [<span data-ttu-id="02bd4-179">csharp_style_expression_bodied_accessors</span><span class="sxs-lookup"><span data-stu-id="02bd4-179">csharp_style_expression_bodied_accessors</span></span>](ide0027.md#csharp_style_expression_bodied_accessors)
  - [<span data-ttu-id="02bd4-180">csharp_style_expression_bodied_lambdas</span><span class="sxs-lookup"><span data-stu-id="02bd4-180">csharp_style_expression_bodied_lambdas</span></span>](ide0053.md#csharp_style_expression_bodied_lambdas)
  - [<span data-ttu-id="02bd4-181">csharp_style_expression_bodied_local_functions</span><span class="sxs-lookup"><span data-stu-id="02bd4-181">csharp_style_expression_bodied_local_functions</span></span>](ide0061.md#csharp_style_expression_bodied_local_functions)
- [<span data-ttu-id="02bd4-182">패턴 일치 기본 설정</span><span class="sxs-lookup"><span data-stu-id="02bd4-182">Pattern matching preferences</span></span>](pattern-matching-preferences.md)
  - [<span data-ttu-id="02bd4-183">csharp_style_pattern_matching_over_is_with_cast_check</span><span class="sxs-lookup"><span data-stu-id="02bd4-183">csharp_style_pattern_matching_over_is_with_cast_check</span></span>](ide0020-ide0038.md#csharp_style_pattern_matching_over_is_with_cast_check)
  - [<span data-ttu-id="02bd4-184">csharp_style_pattern_matching_over_as_with_null_check</span><span class="sxs-lookup"><span data-stu-id="02bd4-184">csharp_style_pattern_matching_over_as_with_null_check</span></span>](ide0019.md#csharp_style_pattern_matching_over_as_with_null_check)
  - [<span data-ttu-id="02bd4-185">csharp_style_prefer_switch_expression</span><span class="sxs-lookup"><span data-stu-id="02bd4-185">csharp_style_prefer_switch_expression</span></span>](ide0066.md#csharp_style_prefer_switch_expression)
  - [<span data-ttu-id="02bd4-186">csharp_style_prefer_pattern_matching</span><span class="sxs-lookup"><span data-stu-id="02bd4-186">csharp_style_prefer_pattern_matching</span></span>](ide0078.md#csharp_style_prefer_pattern_matching)
  - [<span data-ttu-id="02bd4-187">csharp_style_prefer_not_pattern</span><span class="sxs-lookup"><span data-stu-id="02bd4-187">csharp_style_prefer_not_pattern</span></span>](ide0083.md#csharp_style_prefer_not_pattern)
- [<span data-ttu-id="02bd4-188">식 수준 기본 설정</span><span class="sxs-lookup"><span data-stu-id="02bd4-188">Expression-level preferences</span></span>](expression-level-preferences.md#c-expression-level-preferences)
  - [<span data-ttu-id="02bd4-189">csharp_style_inlined_variable_declaration</span><span class="sxs-lookup"><span data-stu-id="02bd4-189">csharp_style_inlined_variable_declaration</span></span>](ide0018.md#csharp_style_inlined_variable_declaration)
  - [<span data-ttu-id="02bd4-190">csharp_prefer_simple_default_expression</span><span class="sxs-lookup"><span data-stu-id="02bd4-190">csharp_prefer_simple_default_expression</span></span>](ide0034.md#csharp_prefer_simple_default_expression)
  - [<span data-ttu-id="02bd4-191">csharp_style_pattern_local_over_anonymous_function</span><span class="sxs-lookup"><span data-stu-id="02bd4-191">csharp_style_pattern_local_over_anonymous_function</span></span>](ide0039.md#csharp_style_pattern_local_over_anonymous_function)
  - [<span data-ttu-id="02bd4-192">csharp_style_deconstructed_variable_declaration</span><span class="sxs-lookup"><span data-stu-id="02bd4-192">csharp_style_deconstructed_variable_declaration</span></span>](ide0042.md#csharp_style_deconstructed_variable_declaration)
  - [<span data-ttu-id="02bd4-193">csharp_style_prefer_index_operator</span><span class="sxs-lookup"><span data-stu-id="02bd4-193">csharp_style_prefer_index_operator</span></span>](ide0056.md#csharp_style_prefer_index_operator)
  - [<span data-ttu-id="02bd4-194">csharp_style_prefer_range_operator</span><span class="sxs-lookup"><span data-stu-id="02bd4-194">csharp_style_prefer_range_operator</span></span>](ide0057.md#csharp_style_prefer_range_operator)
  - [<span data-ttu-id="02bd4-195">csharp_style_implicit_object_creation_when_type_is_apparent</span><span class="sxs-lookup"><span data-stu-id="02bd4-195">csharp_style_implicit_object_creation_when_type_is_apparent</span></span>](ide0090.md#csharp_style_implicit_object_creation_when_type_is_apparent)
  - <span data-ttu-id="02bd4-196">[스위치 식에 누락 된 사례 추가](ide0072.md) -이 규칙에는 코드 스타일 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02bd4-196">[Add missing cases to switch expression](ide0072.md) - This rule has no code style option.</span></span>
- [<span data-ttu-id="02bd4-197">"Null" 검사 기본 설정</span><span class="sxs-lookup"><span data-stu-id="02bd4-197">"Null" checking preferences</span></span>](null-checking-preferences.md#c-null-checking-preferences)
  - [<span data-ttu-id="02bd4-198">csharp_style_throw_expression</span><span class="sxs-lookup"><span data-stu-id="02bd4-198">csharp_style_throw_expression</span></span>](ide0016.md#csharp_style_throw_expression)
  - [<span data-ttu-id="02bd4-199">csharp_style_conditional_delegate_call</span><span class="sxs-lookup"><span data-stu-id="02bd4-199">csharp_style_conditional_delegate_call</span></span>](ide1005.md#csharp_style_conditional_delegate_call)
- [<span data-ttu-id="02bd4-200">코드 블록 기본 설정</span><span class="sxs-lookup"><span data-stu-id="02bd4-200">Code block preferences</span></span>](code-block-preferences.md)
  - [<span data-ttu-id="02bd4-201">csharp_prefer_braces</span><span class="sxs-lookup"><span data-stu-id="02bd4-201">csharp_prefer_braces</span></span>](ide0011.md#csharp_prefer_braces)
  - [<span data-ttu-id="02bd4-202">csharp_prefer_simple_using_statement</span><span class="sxs-lookup"><span data-stu-id="02bd4-202">csharp_prefer_simple_using_statement</span></span>](ide0063.md#csharp_prefer_simple_using_statement)
- [<span data-ttu-id="02bd4-203">' using ' 지시문 기본 설정</span><span class="sxs-lookup"><span data-stu-id="02bd4-203">'using' directive preferences</span></span>](ide0065.md)
  - [<span data-ttu-id="02bd4-204">csharp_using_directive_placement</span><span class="sxs-lookup"><span data-stu-id="02bd4-204">csharp_using_directive_placement</span></span>](ide0065.md#csharp_using_directive_placement)
- [<span data-ttu-id="02bd4-205">한정자 기본 설정</span><span class="sxs-lookup"><span data-stu-id="02bd4-205">Modifier preferences</span></span>](modifier-preferences.md#c-modifier-preferences)
  - [<span data-ttu-id="02bd4-206">csharp_prefer_static_local_function</span><span class="sxs-lookup"><span data-stu-id="02bd4-206">csharp_prefer_static_local_function</span></span>](ide0062.md#csharp_prefer_static_local_function)
  - <span data-ttu-id="02bd4-207">[구조체 필드를 쓰기 가능 하 게 설정](ide0064.md) -이 규칙에는 코드 스타일 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02bd4-207">[Make struct fields writable](ide0064.md) - This rule has no code style option.</span></span>

## <a name="visual-basic-style-rules"></a><span data-ttu-id="02bd4-208">Visual Basic 스타일 규칙</span><span class="sxs-lookup"><span data-stu-id="02bd4-208">Visual Basic style rules</span></span>

<span data-ttu-id="02bd4-209">이 섹션의 스타일 규칙은 Visual Basic 언어에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02bd4-209">The style rules in this section are applicable to Visual Basic language only.</span></span>

- [<span data-ttu-id="02bd4-210">패턴 일치 기본 설정</span><span class="sxs-lookup"><span data-stu-id="02bd4-210">Pattern matching preferences</span></span>](pattern-matching-preferences.md)
  - [<span data-ttu-id="02bd4-211">visual_basic_style_prefer_isnot_expression</span><span class="sxs-lookup"><span data-stu-id="02bd4-211">visual_basic_style_prefer_isnot_expression</span></span>](ide0084.md#visual_basic_style_prefer_isnot_expression)

## <a name="see-also"></a><span data-ttu-id="02bd4-212">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02bd4-212">See also</span></span>

- [<span data-ttu-id="02bd4-213">불필요한 코드 규칙</span><span class="sxs-lookup"><span data-stu-id="02bd4-213">Unnecessary code rules</span></span>](unnecessary-code-rules.md)
- [<span data-ttu-id="02bd4-214">서식 지정 규칙</span><span class="sxs-lookup"><span data-stu-id="02bd4-214">Formatting rules</span></span>](formatting-rules.md)
- [<span data-ttu-id="02bd4-215">이름 지정 규칙</span><span class="sxs-lookup"><span data-stu-id="02bd4-215">Naming rules</span></span>](naming-rules.md)
- [<span data-ttu-id="02bd4-216">.NET 코드 스타일 규칙 참조</span><span class="sxs-lookup"><span data-stu-id="02bd4-216">.NET code style rules reference</span></span>](index.md)
