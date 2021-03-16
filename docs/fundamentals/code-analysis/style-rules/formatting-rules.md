---
title: 코드 스타일 서식 지정 규칙
description: 들여쓰기, 공백, 새 줄의 서식을 지정하는 코드 스타일 규칙에 대해 알아봅니다.
ms.date: 09/25/2020
ms.topic: reference
author: gewarren
ms.author: gewarren
dev_langs:
- CSharp
- VB
f1_keywords:
- IDE0055
- formatting rules
helpviewer_keywords:
- IDE0055
- formatting code style rules [EditorConfig]
- formatting rules
- EditorConfig formatting conventions
ms.openlocfilehash: 866949692341f65a5b78c7dd5b8eec918873d3b7
ms.sourcegitcommit: 1d3af230ec30d8d061be7a887f6ba38a530c4ece
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2021
ms.locfileid: "102511803"
---
# <a name="formatting-rules"></a><span data-ttu-id="d8f73-103">서식 지정 규칙</span><span class="sxs-lookup"><span data-stu-id="d8f73-103">Formatting rules</span></span>

<span data-ttu-id="d8f73-104">서식 지정 규칙은 들여쓰기, 공백, 새 줄이 .NET 프로그래밍 언어 구문 주위에 정렬되는 방식에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-104">Formatting rules affect how indentation, spaces, and new lines are aligned around .NET programming language constructs.</span></span> <span data-ttu-id="d8f73-105">이 규칙은 다음 범주로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-105">The rules fall into the following categories:</span></span>

- <span data-ttu-id="d8f73-106">[.NET 서식 지정 규칙](#net-formatting-rules): C# 및 Visual Basic 모두에 적용되는 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-106">[.NET formatting rules](#net-formatting-rules): Rules that apply to both C# and Visual Basic.</span></span> <span data-ttu-id="d8f73-107">이러한 규칙에 대한 EditorConfig 옵션 이름은 `dotnet_` 접두사로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-107">The EditorConfig option names for these rules start with `dotnet_` prefix.</span></span>
- <span data-ttu-id="d8f73-108">[C# 서식 지정 규칙](#c-formatting-rules): C# 언어에만 적용되는 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-108">[C# formatting rules](#c-formatting-rules): Rules that are specific to C# language only.</span></span> <span data-ttu-id="d8f73-109">이러한 규칙에 대한 EditorConfig 옵션 이름은 `csharp_` 접두사로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-109">The EditorConfig option names for these rules start with `csharp_` prefix.</span></span>

## <a name="rule-id-ide0055-fix-formatting"></a><span data-ttu-id="d8f73-110">규칙 ID: "IDE0055"(서식 수정)</span><span class="sxs-lookup"><span data-stu-id="d8f73-110">Rule ID: "IDE0055" (Fix formatting)</span></span>

<span data-ttu-id="d8f73-111">모든 서식 옵션에는 규칙 ID `IDE0055`와 제목 `Fix formatting`이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-111">All formatting options have rule ID `IDE0055` and title `Fix formatting`.</span></span> <span data-ttu-id="d8f73-112">다음 구성 줄을 사용하여 EditorConfig 파일에서 서식 지정 위반의 심각도를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-112">Set the severity of a formatting violation in an EditorConfig file using the following configuration line.</span></span>

```ini
dotnet_diagnostic.IDE0055.severity = <severity value>
```

<span data-ttu-id="d8f73-113">심각도 값은 [빌드 시 적용](../overview.md#code-style-analysis)해야 하는 `warning` 또는 `error`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-113">The severity value must be `warning` or `error` to be [enforced on build](../overview.md#code-style-analysis).</span></span> <span data-ttu-id="d8f73-114">가능한 모든 심각도 값은 [심각도 수준](../configuration-options.md#severity-level)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8f73-114">For all possible severity values, see [severity level](../configuration-options.md#severity-level).</span></span>

## <a name="option-format"></a><span data-ttu-id="d8f73-115">옵션 형식</span><span class="sxs-lookup"><span data-stu-id="d8f73-115">Option format</span></span>

<span data-ttu-id="d8f73-116">서식 지정 규칙에 대한 옵션은 EditorConfig 파일에서 다음 형식을 사용하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-116">Options for formatting rules can be specified in an EditorConfig file with the following format:</span></span>

`rule_name = value`

<span data-ttu-id="d8f73-117">대부분의 규칙에서, `value`에 대해 `true`(이 스타일 선호) 또는 `false`(이 스타일 선호 안 함)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-117">For many rules, you specify either `true` (prefer this style) or `false` (do not prefer this style) for `value`.</span></span> <span data-ttu-id="d8f73-118">다른 규칙의 경우 `flush_left`, `before_and_after` 등의 값을 지정하여 규칙을 적용할 시기 및 위치를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-118">For other rules, you specify a value such as `flush_left` or `before_and_after` to describe when and where to apply the rule.</span></span> <span data-ttu-id="d8f73-119">심각도를 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-119">You don't specify a severity.</span></span>

## <a name="net-formatting-rules"></a><span data-ttu-id="d8f73-120">.NET 서식 지정 규칙</span><span class="sxs-lookup"><span data-stu-id="d8f73-120">.NET formatting rules</span></span>

<span data-ttu-id="d8f73-121">이 섹션의 서식 지정 규칙은 C# 및 Visual Basic 모두에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-121">The formatting rules in this section apply to both C# and Visual Basic.</span></span>

- [<span data-ttu-id="d8f73-122">using 구성</span><span class="sxs-lookup"><span data-stu-id="d8f73-122">Organize usings</span></span>](#organize-using-directives)
  - <span data-ttu-id="d8f73-123">dotnet_sort_system_directives_first</span><span class="sxs-lookup"><span data-stu-id="d8f73-123">dotnet_sort_system_directives_first</span></span>
  - <span data-ttu-id="d8f73-124">dotnet_separate_import_directive_groups</span><span class="sxs-lookup"><span data-stu-id="d8f73-124">dotnet_separate_import_directive_groups</span></span>

### <a name="organize-using-directives"></a><span data-ttu-id="d8f73-125">using 지시문 구성</span><span class="sxs-lookup"><span data-stu-id="d8f73-125">Organize using directives</span></span>

<span data-ttu-id="d8f73-126">이러한 서식 지정 규칙은 `using` 지시문과 `Imports` 문의 정렬 및 표시를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-126">These formatting rules concern the sorting and display of `using` directives and `Imports` statements.</span></span>

<span data-ttu-id="d8f73-127">예제 *.editorconfig* 파일:</span><span class="sxs-lookup"><span data-stu-id="d8f73-127">Example *.editorconfig* file:</span></span>

```ini
# .NET formatting rules
[*.{cs,vb}]
dotnet_sort_system_directives_first = true
dotnet_separate_import_directive_groups = true
```

#### <a name="dotnet_sort_system_directives_first"></a><span data-ttu-id="d8f73-128">dotnet\_sort\_system\_directives_first</span><span class="sxs-lookup"><span data-stu-id="d8f73-128">dotnet\_sort\_system\_directives_first</span></span>

|<span data-ttu-id="d8f73-129">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-129">Property</span></span>|<span data-ttu-id="d8f73-130">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-130">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-131">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-131">**Option name**</span></span> | <span data-ttu-id="d8f73-132">dotnet_sort_system_directives_first</span><span class="sxs-lookup"><span data-stu-id="d8f73-132">dotnet_sort_system_directives_first</span></span> |
| <span data-ttu-id="d8f73-133">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-133">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-134">C# 및 Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d8f73-134">C# and Visual Basic</span></span> |
| <span data-ttu-id="d8f73-135">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-135">**Introduced version**</span></span> | <span data-ttu-id="d8f73-136">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d8f73-136">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d8f73-137">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-137">**Option values**</span></span> | <span data-ttu-id="d8f73-138">`true` - `System.*` `using` 지시문을 사전순으로 정렬하고 다른 using 지시문 앞에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-138">`true` - Sort `System.*` `using` directives alphabetically, and place them before other using directives.</span></span><br /><br /><span data-ttu-id="d8f73-139">`false` - `System.*` `using` 지시문을 다른 `using` 지시문 앞에 배치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-139">`false` - Do not place `System.*` `using` directives before other `using` directives.</span></span> |

<span data-ttu-id="d8f73-140">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-140">Code examples:</span></span>

```csharp
// dotnet_sort_system_directives_first = true
using System.Collections.Generic;
using System.Threading.Tasks;
using Octokit;

// dotnet_sort_system_directives_first = false
using System.Collections.Generic;
using Octokit;
using System.Threading.Tasks;
```

#### <a name="dotnet_separate_import_directive_groups"></a><span data-ttu-id="d8f73-141">dotnet\_separate\_import\_directive\_groups</span><span class="sxs-lookup"><span data-stu-id="d8f73-141">dotnet\_separate\_import\_directive\_groups</span></span>

|<span data-ttu-id="d8f73-142">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-142">Property</span></span>|<span data-ttu-id="d8f73-143">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-143">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-144">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-144">**Option name**</span></span> | <span data-ttu-id="d8f73-145">dotnet_separate_import_directive_groups</span><span class="sxs-lookup"><span data-stu-id="d8f73-145">dotnet_separate_import_directive_groups</span></span> |
| <span data-ttu-id="d8f73-146">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-146">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-147">C# 및 Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d8f73-147">C# and Visual Basic</span></span> |
| <span data-ttu-id="d8f73-148">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-148">**Introduced version**</span></span> | <span data-ttu-id="d8f73-149">Visual Studio 2017 15.5 버전</span><span class="sxs-lookup"><span data-stu-id="d8f73-149">Visual Studio 2017 version 15.5</span></span> |
| <span data-ttu-id="d8f73-150">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-150">**Option values**</span></span> | <span data-ttu-id="d8f73-151">`true` - `using` 지시문 그룹 사이에 빈 줄을 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-151">`true` - Place a blank line between `using` directive groups.</span></span><br /><br /><span data-ttu-id="d8f73-152">`false` - `using` 지시문 그룹 사이에 빈 줄을 넣지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-152">`false` - Do not place a blank line between `using` directive groups.</span></span> |

<span data-ttu-id="d8f73-153">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-153">Code examples:</span></span>

```csharp
// dotnet_separate_import_directive_groups = true
using System.Collections.Generic;
using System.Threading.Tasks;

using Octokit;

// dotnet_separate_import_directive_groups = false
using System.Collections.Generic;
using System.Threading.Tasks;
using Octokit;
```

## <a name="c-formatting-rules"></a><span data-ttu-id="d8f73-154">C# 서식 지정 규칙</span><span class="sxs-lookup"><span data-stu-id="d8f73-154">C# formatting rules</span></span>

<span data-ttu-id="d8f73-155">이 섹션의 서식 설정 규칙은 C# 코드에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-155">The formatting rules in this section apply only to C# code.</span></span>

- [<span data-ttu-id="d8f73-156">줄 바꿈 옵션</span><span class="sxs-lookup"><span data-stu-id="d8f73-156">Newline options</span></span>](#new-line-options)
  - <span data-ttu-id="d8f73-157">csharp_new_line_before_open_brace</span><span class="sxs-lookup"><span data-stu-id="d8f73-157">csharp_new_line_before_open_brace</span></span>
  - <span data-ttu-id="d8f73-158">csharp_new_line_before_else</span><span class="sxs-lookup"><span data-stu-id="d8f73-158">csharp_new_line_before_else</span></span>
  - <span data-ttu-id="d8f73-159">csharp_new_line_before_catch</span><span class="sxs-lookup"><span data-stu-id="d8f73-159">csharp_new_line_before_catch</span></span>
  - <span data-ttu-id="d8f73-160">csharp_new_line_before_finally</span><span class="sxs-lookup"><span data-stu-id="d8f73-160">csharp_new_line_before_finally</span></span>
  - <span data-ttu-id="d8f73-161">csharp_new_line_before_members_in_object_initializers</span><span class="sxs-lookup"><span data-stu-id="d8f73-161">csharp_new_line_before_members_in_object_initializers</span></span>
  - <span data-ttu-id="d8f73-162">csharp_new_line_before_members_in_anonymous_types</span><span class="sxs-lookup"><span data-stu-id="d8f73-162">csharp_new_line_before_members_in_anonymous_types</span></span>
  - <span data-ttu-id="d8f73-163">csharp_new_line_between_query_expression_clauses</span><span class="sxs-lookup"><span data-stu-id="d8f73-163">csharp_new_line_between_query_expression_clauses</span></span>
- [<span data-ttu-id="d8f73-164">들여쓰기 옵션</span><span class="sxs-lookup"><span data-stu-id="d8f73-164">Indentation options</span></span>](#indentation-options)
  - <span data-ttu-id="d8f73-165">csharp_indent_case_contents</span><span class="sxs-lookup"><span data-stu-id="d8f73-165">csharp_indent_case_contents</span></span>
  - <span data-ttu-id="d8f73-166">csharp_indent_switch_labels</span><span class="sxs-lookup"><span data-stu-id="d8f73-166">csharp_indent_switch_labels</span></span>
  - <span data-ttu-id="d8f73-167">csharp_indent_labels</span><span class="sxs-lookup"><span data-stu-id="d8f73-167">csharp_indent_labels</span></span>
  - <span data-ttu-id="d8f73-168">csharp_indent_block_contents</span><span class="sxs-lookup"><span data-stu-id="d8f73-168">csharp_indent_block_contents</span></span>
  - <span data-ttu-id="d8f73-169">csharp_indent_braces</span><span class="sxs-lookup"><span data-stu-id="d8f73-169">csharp_indent_braces</span></span>
  - <span data-ttu-id="d8f73-170">csharp_indent_case_contents_when_block</span><span class="sxs-lookup"><span data-stu-id="d8f73-170">csharp_indent_case_contents_when_block</span></span>
- [<span data-ttu-id="d8f73-171">간격 옵션</span><span class="sxs-lookup"><span data-stu-id="d8f73-171">Spacing options</span></span>](#spacing-options)
  - <span data-ttu-id="d8f73-172">csharp_space_after_cast</span><span class="sxs-lookup"><span data-stu-id="d8f73-172">csharp_space_after_cast</span></span>
  - <span data-ttu-id="d8f73-173">csharp_space_after_keywords_in_control_flow_statements</span><span class="sxs-lookup"><span data-stu-id="d8f73-173">csharp_space_after_keywords_in_control_flow_statements</span></span>
  - <span data-ttu-id="d8f73-174">csharp_space_between_parentheses</span><span class="sxs-lookup"><span data-stu-id="d8f73-174">csharp_space_between_parentheses</span></span>
  - <span data-ttu-id="d8f73-175">csharp_space_before_colon_in_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="d8f73-175">csharp_space_before_colon_in_inheritance_clause</span></span>
  - <span data-ttu-id="d8f73-176">csharp_space_after_colon_in_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="d8f73-176">csharp_space_after_colon_in_inheritance_clause</span></span>
  - <span data-ttu-id="d8f73-177">csharp_space_around_binary_operators</span><span class="sxs-lookup"><span data-stu-id="d8f73-177">csharp_space_around_binary_operators</span></span>
  - <span data-ttu-id="d8f73-178">csharp_space_between_method_declaration_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="d8f73-178">csharp_space_between_method_declaration_parameter_list_parentheses</span></span>
  - <span data-ttu-id="d8f73-179">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="d8f73-179">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span></span>
  - <span data-ttu-id="d8f73-180">csharp_space_between_method_declaration_name_and_open_parenthesis</span><span class="sxs-lookup"><span data-stu-id="d8f73-180">csharp_space_between_method_declaration_name_and_open_parenthesis</span></span>
  - <span data-ttu-id="d8f73-181">csharp_space_between_method_call_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="d8f73-181">csharp_space_between_method_call_parameter_list_parentheses</span></span>
  - <span data-ttu-id="d8f73-182">csharp_space_between_method_call_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="d8f73-182">csharp_space_between_method_call_empty_parameter_list_parentheses</span></span>
  - <span data-ttu-id="d8f73-183">csharp_space_between_method_call_name_and_opening_parenthesis</span><span class="sxs-lookup"><span data-stu-id="d8f73-183">csharp_space_between_method_call_name_and_opening_parenthesis</span></span>
  - <span data-ttu-id="d8f73-184">csharp_space_after_comma</span><span class="sxs-lookup"><span data-stu-id="d8f73-184">csharp_space_after_comma</span></span>
  - <span data-ttu-id="d8f73-185">csharp_space_before_comma</span><span class="sxs-lookup"><span data-stu-id="d8f73-185">csharp_space_before_comma</span></span>
  - <span data-ttu-id="d8f73-186">csharp_space_after_dot</span><span class="sxs-lookup"><span data-stu-id="d8f73-186">csharp_space_after_dot</span></span>
  - <span data-ttu-id="d8f73-187">csharp_space_before_dot</span><span class="sxs-lookup"><span data-stu-id="d8f73-187">csharp_space_before_dot</span></span>
  - <span data-ttu-id="d8f73-188">csharp_space_after_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="d8f73-188">csharp_space_after_semicolon_in_for_statement</span></span>
  - <span data-ttu-id="d8f73-189">csharp_space_before_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="d8f73-189">csharp_space_before_semicolon_in_for_statement</span></span>
  - <span data-ttu-id="d8f73-190">csharp_space_around_declaration_statements</span><span class="sxs-lookup"><span data-stu-id="d8f73-190">csharp_space_around_declaration_statements</span></span>
  - <span data-ttu-id="d8f73-191">csharp_space_before_open_square_brackets</span><span class="sxs-lookup"><span data-stu-id="d8f73-191">csharp_space_before_open_square_brackets</span></span>
  - <span data-ttu-id="d8f73-192">csharp_space_between_empty_square_brackets</span><span class="sxs-lookup"><span data-stu-id="d8f73-192">csharp_space_between_empty_square_brackets</span></span>
  - <span data-ttu-id="d8f73-193">csharp_space_between_square_brackets</span><span class="sxs-lookup"><span data-stu-id="d8f73-193">csharp_space_between_square_brackets</span></span>
- [<span data-ttu-id="d8f73-194">줄 바꿈 옵션</span><span class="sxs-lookup"><span data-stu-id="d8f73-194">Wrap options</span></span>](#wrap-options)
  - <span data-ttu-id="d8f73-195">csharp_preserve_single_line_statements</span><span class="sxs-lookup"><span data-stu-id="d8f73-195">csharp_preserve_single_line_statements</span></span>
  - <span data-ttu-id="d8f73-196">csharp_preserve_single_line_blocks</span><span class="sxs-lookup"><span data-stu-id="d8f73-196">csharp_preserve_single_line_blocks</span></span>
- [<span data-ttu-id="d8f73-197">지시문 옵션 사용</span><span class="sxs-lookup"><span data-stu-id="d8f73-197">Using directive options</span></span>](#using-directive-options)
  - <span data-ttu-id="d8f73-198">csharp_using_directive_placement</span><span class="sxs-lookup"><span data-stu-id="d8f73-198">csharp_using_directive_placement</span></span>

### <a name="new-line-options"></a><span data-ttu-id="d8f73-199">줄 바꿈 옵션</span><span class="sxs-lookup"><span data-stu-id="d8f73-199">New-line options</span></span>

<span data-ttu-id="d8f73-200">이러한 서식 지정 규칙은 코드의 서식을 지정하기 위해 새 줄을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-200">These formatting rules concern the use of new lines to format code.</span></span>

<span data-ttu-id="d8f73-201">예제 *.editorconfig* 파일:</span><span class="sxs-lookup"><span data-stu-id="d8f73-201">Example *.editorconfig* file:</span></span>

```ini
# CSharp formatting rules:
[*.cs]
csharp_new_line_before_open_brace = methods, properties, control_blocks, types
csharp_new_line_before_else = true
csharp_new_line_before_catch = true
csharp_new_line_before_finally = true
csharp_new_line_before_members_in_object_initializers = true
csharp_new_line_before_members_in_anonymous_types = true
csharp_new_line_between_query_expression_clauses = true
```

#### <a name="csharp_new_line_before_open_brace"></a><span data-ttu-id="d8f73-202">csharp\_new\_line\_before\_open_brace</span><span class="sxs-lookup"><span data-stu-id="d8f73-202">csharp\_new\_line\_before\_open_brace</span></span>

<span data-ttu-id="d8f73-203">이 규칙은 중괄호 `{`가 앞의 코드와 동일한 줄 또는 새 줄에 배치되어야 하는지를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-203">This rule concerns whether an open brace `{` should be placed on the same line as the preceding code, or on a new line.</span></span> <span data-ttu-id="d8f73-204">이 규칙의 경우 **모두**, **없음** 또는 하나 이상의 코드 요소(예: **메서드** 또는 **속성**)를 지정하여 이 규칙을 적용할 시점을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-204">For this rule, you specify **all**, **none**, or one or more code elements such as **methods** or **properties**, to define when this rule should be applied.</span></span> <span data-ttu-id="d8f73-205">여러 개의 코드 요소를 지정하려면 쉼표(,)로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-205">To specify multiple code elements, separate them with a comma (,).</span></span>

|<span data-ttu-id="d8f73-206">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-206">Property</span></span>|<span data-ttu-id="d8f73-207">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-207">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-208">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-208">**Option name**</span></span> | <span data-ttu-id="d8f73-209">csharp_new_line_before_open_brace</span><span class="sxs-lookup"><span data-stu-id="d8f73-209">csharp_new_line_before_open_brace</span></span> |
| <span data-ttu-id="d8f73-210">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-210">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-211">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-211">C#</span></span> |
| <span data-ttu-id="d8f73-212">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-212">**Introduced version**</span></span> | <span data-ttu-id="d8f73-213">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d8f73-213">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d8f73-214">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-214">**Option values**</span></span> | <span data-ttu-id="d8f73-215">`all` - 모든 식에서 중괄호를 새 줄에 배치해야 합니다(“Allman” 스타일).</span><span class="sxs-lookup"><span data-stu-id="d8f73-215">`all` - Require braces to be on a new line for all expressions ("Allman" style).</span></span><br /><br /><span data-ttu-id="d8f73-216">`none` - 모든 식에서 중괄호를 동일한 줄에 배치해야 합니다(“K&R”).</span><span class="sxs-lookup"><span data-stu-id="d8f73-216">`none` - Require braces to be on the same line for all expressions ("K&R").</span></span><br /><br /><span data-ttu-id="d8f73-217">`accessors`, `anonymous_methods`, `anonymous_types`, `control_blocks`, `events`, `indexers`, `lambdas`, `local_functions`, `methods`, `object_collection_array_initializers`, `properties`, `types` - 지정된 코드 요소에서 중괄호를 새 줄에 배치해야 합니다(“Allman” 스타일).</span><span class="sxs-lookup"><span data-stu-id="d8f73-217">`accessors`, `anonymous_methods`, `anonymous_types`, `control_blocks`, `events`, `indexers`, `lambdas`, `local_functions`, `methods`, `object_collection_array_initializers`, `properties`, `types` - Require braces to be on a new line for the specified code element ("Allman" style).</span></span> |

<span data-ttu-id="d8f73-218">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-218">Code examples:</span></span>

```csharp
// csharp_new_line_before_open_brace = all
void MyMethod()
{
    if (...)
    {
        ...
    }
}

// csharp_new_line_before_open_brace = none
void MyMethod() {
    if (...) {
        ...
    }
}
```

#### <a name="csharp_new_line_before_else"></a><span data-ttu-id="d8f73-219">csharp\_new\_line\_before_else</span><span class="sxs-lookup"><span data-stu-id="d8f73-219">csharp\_new\_line\_before_else</span></span>

|<span data-ttu-id="d8f73-220">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-220">Property</span></span>|<span data-ttu-id="d8f73-221">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-221">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-222">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-222">**Option name**</span></span> | <span data-ttu-id="d8f73-223">csharp_new_line_before_else</span><span class="sxs-lookup"><span data-stu-id="d8f73-223">csharp_new_line_before_else</span></span> |
| <span data-ttu-id="d8f73-224">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-224">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-225">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-225">C#</span></span> |
| <span data-ttu-id="d8f73-226">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-226">**Introduced version**</span></span> | <span data-ttu-id="d8f73-227">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d8f73-227">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d8f73-228">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-228">**Option values**</span></span> | <span data-ttu-id="d8f73-229">`true` - `else` 문을 새 줄에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-229">`true` - Place `else` statements on a new line.</span></span><br /><br /><span data-ttu-id="d8f73-230">`false` - `else` 문을 동일한 줄에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-230">`false` - Place `else` statements on the same line.</span></span> |

<span data-ttu-id="d8f73-231">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-231">Code examples:</span></span>

```csharp
// csharp_new_line_before_else = true
if (...) {
    ...
}
else {
    ...
}

// csharp_new_line_before_else = false
if (...) {
    ...
} else {
    ...
}
```

#### <a name="csharp_new_line_before_catch"></a><span data-ttu-id="d8f73-232">csharp\_new\_line\_before_catch</span><span class="sxs-lookup"><span data-stu-id="d8f73-232">csharp\_new\_line\_before_catch</span></span>

|<span data-ttu-id="d8f73-233">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-233">Property</span></span>|<span data-ttu-id="d8f73-234">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-234">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-235">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-235">**Option name**</span></span> | <span data-ttu-id="d8f73-236">csharp_new_line_before_catch</span><span class="sxs-lookup"><span data-stu-id="d8f73-236">csharp_new_line_before_catch</span></span> |
| <span data-ttu-id="d8f73-237">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-237">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-238">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-238">C#</span></span> |
| <span data-ttu-id="d8f73-239">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-239">**Introduced version**</span></span> | <span data-ttu-id="d8f73-240">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d8f73-240">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d8f73-241">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-241">**Option values**</span></span> | <span data-ttu-id="d8f73-242">`true` - `catch` 문을 새 줄에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-242">`true` - Place `catch` statements on a new line.</span></span><br /><br /><span data-ttu-id="d8f73-243">`false` - `catch` 문을 동일한 줄에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-243">`false` - Place `catch` statements on the same line.</span></span> |

<span data-ttu-id="d8f73-244">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-244">Code examples:</span></span>

```csharp
// csharp_new_line_before_catch = true
try {
    ...
}
catch (Exception e) {
    ...
}

// csharp_new_line_before_catch = false
try {
    ...
} catch (Exception e) {
    ...
}
```

#### <a name="csharp_new_line_before_finally"></a><span data-ttu-id="d8f73-245">csharp\_new\_line\_before_finally</span><span class="sxs-lookup"><span data-stu-id="d8f73-245">csharp\_new\_line\_before_finally</span></span>

|<span data-ttu-id="d8f73-246">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-246">Property</span></span>|<span data-ttu-id="d8f73-247">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-247">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-248">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-248">**Option name**</span></span> | <span data-ttu-id="d8f73-249">csharp_new_line_before_finally</span><span class="sxs-lookup"><span data-stu-id="d8f73-249">csharp_new_line_before_finally</span></span> |
| <span data-ttu-id="d8f73-250">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-250">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-251">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-251">C#</span></span> |
| <span data-ttu-id="d8f73-252">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-252">**Introduced version**</span></span> | <span data-ttu-id="d8f73-253">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d8f73-253">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d8f73-254">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-254">**Option values**</span></span> | <span data-ttu-id="d8f73-255">`true` - `finally` 문을 닫는 괄호 뒤의 새 줄에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-255">`true` - Require `finally` statements to be on a new line after the closing brace.</span></span><br /><br /><span data-ttu-id="d8f73-256">`false` - `finally` 문을 닫는 괄호와 동일한 줄에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-256">`false` - Require `finally` statements to be on the same line as the closing brace.</span></span> |

<span data-ttu-id="d8f73-257">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-257">Code examples:</span></span>

```csharp
// csharp_new_line_before_finally = true
try {
    ...
}
catch (Exception e) {
    ...
}
finally {
    ...
}

// csharp_new_line_before_finally = false
try {
    ...
} catch (Exception e) {
    ...
} finally {
    ...
}
```

#### <a name="csharp_new_line_before_members_in_object_initializers"></a><span data-ttu-id="d8f73-258">csharp\_new\_line\_before\_members\_in\_object_initializers</span><span class="sxs-lookup"><span data-stu-id="d8f73-258">csharp\_new\_line\_before\_members\_in\_object_initializers</span></span>

|<span data-ttu-id="d8f73-259">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-259">Property</span></span>|<span data-ttu-id="d8f73-260">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-260">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-261">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-261">**Option name**</span></span> | <span data-ttu-id="d8f73-262">csharp_new_line_before_members_in_object_initializers</span><span class="sxs-lookup"><span data-stu-id="d8f73-262">csharp_new_line_before_members_in_object_initializers</span></span> |
| <span data-ttu-id="d8f73-263">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-263">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-264">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-264">C#</span></span> |
| <span data-ttu-id="d8f73-265">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-265">**Introduced version**</span></span> | <span data-ttu-id="d8f73-266">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d8f73-266">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d8f73-267">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-267">**Option values**</span></span> | <span data-ttu-id="d8f73-268">`true` - 개체 이니셜라이저의 멤버를 새 줄에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-268">`true` - Require members of object initializers to be on separate lines</span></span><br /><br /><span data-ttu-id="d8f73-269">`false` - 개체 이니셜라이저의 멤버를 동일한 줄에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-269">`false` - Require members of object initializers to be on the same line</span></span> |

<span data-ttu-id="d8f73-270">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-270">Code examples:</span></span>

```csharp
// csharp_new_line_before_members_in_object_initializers = true
var z = new B()
{
    A = 3,
    B = 4
}

// csharp_new_line_before_members_in_object_initializers = false
var z = new B()
{
    A = 3, B = 4
}
```

#### <a name="csharp_new_line_before_members_in_anonymous_types"></a><span data-ttu-id="d8f73-271">csharp\_new\_line\_before\_members\_in\_anonymous_types</span><span class="sxs-lookup"><span data-stu-id="d8f73-271">csharp\_new\_line\_before\_members\_in\_anonymous_types</span></span>

|<span data-ttu-id="d8f73-272">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-272">Property</span></span>|<span data-ttu-id="d8f73-273">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-273">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-274">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-274">**Option name**</span></span> | <span data-ttu-id="d8f73-275">csharp_new_line_before_members_in_anonymous_types</span><span class="sxs-lookup"><span data-stu-id="d8f73-275">csharp_new_line_before_members_in_anonymous_types</span></span> |
| <span data-ttu-id="d8f73-276">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-276">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-277">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-277">C#</span></span> |
| <span data-ttu-id="d8f73-278">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-278">**Introduced version**</span></span> | <span data-ttu-id="d8f73-279">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d8f73-279">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d8f73-280">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-280">**Option values**</span></span> | <span data-ttu-id="d8f73-281">`true` - 무명 형식의 멤버를 새 줄에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-281">`true` - Require members of anonymous types to be on separate lines</span></span><br /><br /><span data-ttu-id="d8f73-282">`false` - 무명 형식의 멤버를 동일한 줄에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-282">`false` - Require members of anonymous types to be on the same line</span></span> |

<span data-ttu-id="d8f73-283">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-283">Code examples:</span></span>

```csharp
// csharp_new_line_before_members_in_anonymous_types = true
var z = new
{
    A = 3,
    B = 4
}

// csharp_new_line_before_members_in_anonymous_types = false
var z = new
{
    A = 3, B = 4
}
```

#### <a name="csharp_new_line_between_query_expression_clauses"></a><span data-ttu-id="d8f73-284">csharp_new_line_between_query_expression_clauses</span><span class="sxs-lookup"><span data-stu-id="d8f73-284">csharp_new_line_between_query_expression_clauses</span></span>

|<span data-ttu-id="d8f73-285">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-285">Property</span></span>|<span data-ttu-id="d8f73-286">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-286">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-287">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-287">**Option name**</span></span> | <span data-ttu-id="d8f73-288">csharp_new_line_between_query_expression_clauses</span><span class="sxs-lookup"><span data-stu-id="d8f73-288">csharp_new_line_between_query_expression_clauses</span></span> |
| <span data-ttu-id="d8f73-289">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-289">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-290">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-290">C#</span></span> |
| <span data-ttu-id="d8f73-291">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-291">**Introduced version**</span></span> | <span data-ttu-id="d8f73-292">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d8f73-292">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d8f73-293">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-293">**Option values**</span></span> | <span data-ttu-id="d8f73-294">`true` - 쿼리 식 절의 요소를 새 줄에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-294">`true` - Require elements of query expression clauses to be on separate lines</span></span><br /><br /><span data-ttu-id="d8f73-295">`false` - 쿼리 식 절의 요소를 동일한 줄에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-295">`false` - Require elements of query expression clauses to be on the same line</span></span> |

<span data-ttu-id="d8f73-296">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-296">Code examples:</span></span>

```csharp
// csharp_new_line_between_query_expression_clauses = true
var q = from a in e
        from b in e
        select a * b;

// csharp_new_line_between_query_expression_clauses = false
var q = from a in e from b in e
        select a * b;
```

### <a name="indentation-options"></a><span data-ttu-id="d8f73-297">들여쓰기 옵션</span><span class="sxs-lookup"><span data-stu-id="d8f73-297">Indentation options</span></span>

<span data-ttu-id="d8f73-298">이러한 서식 지정 규칙은 코드의 서식을 지정하기 위해 들여쓰기를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-298">These formatting rules concern the use of indentation to format code.</span></span>

<span data-ttu-id="d8f73-299">예제 *.editorconfig* 파일:</span><span class="sxs-lookup"><span data-stu-id="d8f73-299">Example *.editorconfig* file:</span></span>

```ini
# CSharp formatting rules:
[*.cs]
csharp_indent_case_contents = true
csharp_indent_switch_labels = true
csharp_indent_labels = flush_left
csharp_indent_block_contents = true
csharp_indent_braces = false
csharp_indent_case_contents_when_block = true
```

#### <a name="csharp_indent_case_contents"></a><span data-ttu-id="d8f73-300">csharp\_indent\_case_contents</span><span class="sxs-lookup"><span data-stu-id="d8f73-300">csharp\_indent\_case_contents</span></span>

|<span data-ttu-id="d8f73-301">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-301">Property</span></span>|<span data-ttu-id="d8f73-302">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-302">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-303">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-303">**Option name**</span></span> | <span data-ttu-id="d8f73-304">csharp_indent_case_contents</span><span class="sxs-lookup"><span data-stu-id="d8f73-304">csharp_indent_case_contents</span></span> |
| <span data-ttu-id="d8f73-305">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-305">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-306">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-306">C#</span></span> |
| <span data-ttu-id="d8f73-307">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-307">**Introduced version**</span></span> | <span data-ttu-id="d8f73-308">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d8f73-308">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d8f73-309">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-309">**Option values**</span></span> | <span data-ttu-id="d8f73-310">`true` - `switch` case 콘텐츠를 들여씁니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-310">`true` - Indent `switch` case contents</span></span><br /><br /><span data-ttu-id="d8f73-311">`false` - `switch` case 콘텐츠를 들여 쓰지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-311">`false` - Do not indent `switch` case contents</span></span> |

- <span data-ttu-id="d8f73-312">이 규칙을 **true** 로 설정한 경우 i입니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-312">When this rule is set to **true**, i.</span></span>
- <span data-ttu-id="d8f73-313">이 규칙을 **false** 로 설정한 경우 d입니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-313">When this rule is set to **false**, d.</span></span>

<span data-ttu-id="d8f73-314">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-314">Code examples:</span></span>

```csharp
// csharp_indent_case_contents = true
switch(c) {
    case Color.Red:
        Console.WriteLine("The color is red");
        break;
    case Color.Blue:
        Console.WriteLine("The color is blue");
        break;
    default:
        Console.WriteLine("The color is unknown.");
        break;
}

// csharp_indent_case_contents = false
switch(c) {
    case Color.Red:
    Console.WriteLine("The color is red");
    break;
    case Color.Blue:
    Console.WriteLine("The color is blue");
    break;
    default:
    Console.WriteLine("The color is unknown.");
    break;
}
```

#### <a name="csharp_indent_switch_labels"></a><span data-ttu-id="d8f73-315">csharp\_indent\_switch_labels</span><span class="sxs-lookup"><span data-stu-id="d8f73-315">csharp\_indent\_switch_labels</span></span>

|<span data-ttu-id="d8f73-316">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-316">Property</span></span>|<span data-ttu-id="d8f73-317">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-317">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-318">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-318">**Option name**</span></span> | <span data-ttu-id="d8f73-319">csharp_indent_switch_labels</span><span class="sxs-lookup"><span data-stu-id="d8f73-319">csharp_indent_switch_labels</span></span> |
| <span data-ttu-id="d8f73-320">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-320">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-321">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-321">C#</span></span> |
| <span data-ttu-id="d8f73-322">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-322">**Introduced version**</span></span> | <span data-ttu-id="d8f73-323">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d8f73-323">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d8f73-324">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-324">**Option values**</span></span> | <span data-ttu-id="d8f73-325">`true` - `switch` 레이블을 들여씁니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-325">`true` - Indent `switch` labels</span></span><br /><br /><span data-ttu-id="d8f73-326">`false` - `switch` 레이블을 들여 쓰지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-326">`false` - Do not indent `switch` labels</span></span> |

<span data-ttu-id="d8f73-327">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-327">Code examples:</span></span>

```csharp
// csharp_indent_switch_labels = true
switch(c) {
    case Color.Red:
        Console.WriteLine("The color is red");
        break;
    case Color.Blue:
        Console.WriteLine("The color is blue");
        break;
    default:
        Console.WriteLine("The color is unknown.");
        break;
}

// csharp_indent_switch_labels = false
switch(c) {
case Color.Red:
    Console.WriteLine("The color is red");
    break;
case Color.Blue:
    Console.WriteLine("The color is blue");
    break;
default:
    Console.WriteLine("The color is unknown.");
    break;
}
```

#### <a name="csharp_indent_labels"></a><span data-ttu-id="d8f73-328">csharp\_indent_labels</span><span class="sxs-lookup"><span data-stu-id="d8f73-328">csharp\_indent_labels</span></span>

|<span data-ttu-id="d8f73-329">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-329">Property</span></span>|<span data-ttu-id="d8f73-330">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-330">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-331">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-331">**Option name**</span></span> | <span data-ttu-id="d8f73-332">csharp_indent_labels</span><span class="sxs-lookup"><span data-stu-id="d8f73-332">csharp_indent_labels</span></span> |
| <span data-ttu-id="d8f73-333">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-333">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-334">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-334">C#</span></span> |
| <span data-ttu-id="d8f73-335">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-335">**Introduced version**</span></span> | <span data-ttu-id="d8f73-336">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d8f73-336">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d8f73-337">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-337">**Option values**</span></span> | <span data-ttu-id="d8f73-338">`flush_left` - 레이블이 가장 왼쪽 열에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-338">`flush_left` - Labels are placed at the leftmost column</span></span><br /><br /><span data-ttu-id="d8f73-339">`one_less_than_current` - 레이블이 현재 컨텍스트보다 한 수준 더 들여쓰기에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-339">`one_less_than_current` - Labels are placed at one less indent to the current context</span></span><br /><br /><span data-ttu-id="d8f73-340">`no_change` - 레이블이 현재 컨텍스트와 동일한 들여쓰기에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-340">`no_change` - Labels are placed at the same indent as the current context</span></span> |

<span data-ttu-id="d8f73-341">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-341">Code examples:</span></span>

```csharp
// csharp_indent_labels= flush_left
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
error:
        throw new Exception(...);
    }
}

// csharp_indent_labels = one_less_than_current
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
    error:
        throw new Exception(...);
    }
}

// csharp_indent_labels= no_change
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
        error:
        throw new Exception(...);
    }
}
```

#### <a name="csharp_indent_block_contents"></a><span data-ttu-id="d8f73-342">csharp_indent_block_contents</span><span class="sxs-lookup"><span data-stu-id="d8f73-342">csharp_indent_block_contents</span></span>

|<span data-ttu-id="d8f73-343">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-343">Property</span></span>|<span data-ttu-id="d8f73-344">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-344">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-345">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-345">**Option name**</span></span> | <span data-ttu-id="d8f73-346">csharp_indent_block_contents</span><span class="sxs-lookup"><span data-stu-id="d8f73-346">csharp_indent_block_contents</span></span> |
| <span data-ttu-id="d8f73-347">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-347">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-348">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-348">C#</span></span> |
| <span data-ttu-id="d8f73-349">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-349">**Option values**</span></span> | `true` - <br /><br />`false` -  |

<span data-ttu-id="d8f73-350">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-350">Code examples:</span></span>

```csharp
// csharp_indent_block_contents = true
static void Hello()
{
    Console.WriteLine("Hello");
}

// csharp_indent_block_contents = false
static void Hello()
{
Console.WriteLine("Hello");
}
```

#### <a name="csharp_indent_braces"></a><span data-ttu-id="d8f73-351">csharp_indent_braces</span><span class="sxs-lookup"><span data-stu-id="d8f73-351">csharp_indent_braces</span></span>

|<span data-ttu-id="d8f73-352">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-352">Property</span></span>|<span data-ttu-id="d8f73-353">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-353">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-354">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-354">**Option name**</span></span> | <span data-ttu-id="d8f73-355">csharp_indent_braces</span><span class="sxs-lookup"><span data-stu-id="d8f73-355">csharp_indent_braces</span></span> |
| <span data-ttu-id="d8f73-356">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-356">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-357">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-357">C#</span></span> |
| <span data-ttu-id="d8f73-358">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-358">**Option values**</span></span> | `true` - <br /><br />`false` -  |

<span data-ttu-id="d8f73-359">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-359">Code examples:</span></span>

```csharp
// csharp_indent_braces = true
static void Hello()
    {
    Console.WriteLine("Hello");
    }

// csharp_indent_braces = false
static void Hello()
{
    Console.WriteLine("Hello");
}
```

#### <a name="csharp_indent_case_contents_when_block"></a><span data-ttu-id="d8f73-360">csharp_indent_case_contents_when_block</span><span class="sxs-lookup"><span data-stu-id="d8f73-360">csharp_indent_case_contents_when_block</span></span>

|<span data-ttu-id="d8f73-361">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-361">Property</span></span>|<span data-ttu-id="d8f73-362">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-362">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-363">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-363">**Option name**</span></span> | <span data-ttu-id="d8f73-364">csharp_indent_case_contents_when_block</span><span class="sxs-lookup"><span data-stu-id="d8f73-364">csharp_indent_case_contents_when_block</span></span> |
| <span data-ttu-id="d8f73-365">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-365">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-366">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-366">C#</span></span> |
| <span data-ttu-id="d8f73-367">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-367">**Option values**</span></span> | `true` - <br /><br />`false` -  |

<span data-ttu-id="d8f73-368">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-368">Code examples:</span></span>

```csharp
// csharp_indent_case_contents_when_block = true
case 0:
    {
        Console.WriteLine("Hello");
        break;
    }

// csharp_indent_case_contents_when_block = false
case 0:
{
    Console.WriteLine("Hello");
    break;
}
```

### <a name="spacing-options"></a><span data-ttu-id="d8f73-369">간격 옵션</span><span class="sxs-lookup"><span data-stu-id="d8f73-369">Spacing options</span></span>

<span data-ttu-id="d8f73-370">이러한 서식 지정 규칙은 코드의 서식을 지정하기 위해 공백 문자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-370">These formatting rules concern the use of space characters to format code.</span></span>

<span data-ttu-id="d8f73-371">예제 *.editorconfig* 파일:</span><span class="sxs-lookup"><span data-stu-id="d8f73-371">Example *.editorconfig* file:</span></span>

```ini
# CSharp formatting rules:
[*.cs]
csharp_space_after_cast = true
csharp_space_after_keywords_in_control_flow_statements = true
csharp_space_between_parentheses = control_flow_statements, type_casts
csharp_space_before_colon_in_inheritance_clause = true
csharp_space_after_colon_in_inheritance_clause = true
csharp_space_around_binary_operators = before_and_after
csharp_space_between_method_declaration_parameter_list_parentheses = true
csharp_space_between_method_declaration_empty_parameter_list_parentheses = false
csharp_space_between_method_declaration_name_and_open_parenthesis = false
csharp_space_between_method_call_parameter_list_parentheses = true
csharp_space_between_method_call_empty_parameter_list_parentheses = false
csharp_space_between_method_call_name_and_opening_parenthesis = false
csharp_space_after_comma = true
csharp_space_before_comma = false
csharp_space_after_dot = false
csharp_space_before_dot = false
csharp_space_after_semicolon_in_for_statement = true
csharp_space_before_semicolon_in_for_statement = false
csharp_space_around_declaration_statements = false
csharp_space_before_open_square_brackets = false
csharp_space_between_empty_square_brackets = false
csharp_space_between_square_brackets = false
```

#### <a name="csharp_space_after_cast"></a><span data-ttu-id="d8f73-372">csharp\_space\_after_cast</span><span class="sxs-lookup"><span data-stu-id="d8f73-372">csharp\_space\_after_cast</span></span>

|<span data-ttu-id="d8f73-373">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-373">Property</span></span>|<span data-ttu-id="d8f73-374">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-374">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-375">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-375">**Option name**</span></span> | <span data-ttu-id="d8f73-376">csharp_space_after_cast</span><span class="sxs-lookup"><span data-stu-id="d8f73-376">csharp_space_after_cast</span></span> |
| <span data-ttu-id="d8f73-377">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-377">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-378">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-378">C#</span></span> |
| <span data-ttu-id="d8f73-379">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-379">**Introduced version**</span></span> | <span data-ttu-id="d8f73-380">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d8f73-380">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d8f73-381">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-381">**Option values**</span></span> | <span data-ttu-id="d8f73-382">`true` - 캐스트와 값 사이에 공백 문자를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-382">`true` - Place a space character between a cast and the value</span></span><br /><br /><span data-ttu-id="d8f73-383">`false` - 캐스트와 값 사이에서 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-383">`false` - Remove space between the cast and the value</span></span> |

<span data-ttu-id="d8f73-384">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-384">Code examples:</span></span>

```csharp
// csharp_space_after_cast = true
int y = (int) x;

// csharp_space_after_cast = false
int y = (int)x;
```

#### <a name="csharp_space_after_keywords_in_control_flow_statements"></a><span data-ttu-id="d8f73-385">csharp_space_after_keywords_in_control_flow_statements</span><span class="sxs-lookup"><span data-stu-id="d8f73-385">csharp_space_after_keywords_in_control_flow_statements</span></span>

|<span data-ttu-id="d8f73-386">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-386">Property</span></span>|<span data-ttu-id="d8f73-387">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-387">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-388">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-388">**Option name**</span></span> | <span data-ttu-id="d8f73-389">csharp_space_after_keywords_in_control_flow_statements</span><span class="sxs-lookup"><span data-stu-id="d8f73-389">csharp_space_after_keywords_in_control_flow_statements</span></span> |
| <span data-ttu-id="d8f73-390">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-390">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-391">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-391">C#</span></span> |
| <span data-ttu-id="d8f73-392">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-392">**Introduced version**</span></span> | <span data-ttu-id="d8f73-393">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d8f73-393">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d8f73-394">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-394">**Option values**</span></span> | <span data-ttu-id="d8f73-395">`true` - `for` 루프와 같은 제어 흐름 문의 키워드 뒤에 공백 문자를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-395">`true` - Place a space character after a keyword in a control flow statement such as a `for` loop</span></span><br /><br /><span data-ttu-id="d8f73-396">`false` - `for` 루프와 같은 제어 흐름 문의 키워드 뒤에서 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-396">`false` - Remove space after a keyword in a control flow statement such as a `for` loop</span></span> |

<span data-ttu-id="d8f73-397">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-397">Code examples:</span></span>

```csharp
// csharp_space_after_keywords_in_control_flow_statements = true
for (int i;i<x;i++) { ... }

// csharp_space_after_keywords_in_control_flow_statements = false
for(int i;i<x;i++) { ... }
```

#### <a name="csharp_space_between_parentheses"></a><span data-ttu-id="d8f73-398">csharp_space_between_parentheses</span><span class="sxs-lookup"><span data-stu-id="d8f73-398">csharp_space_between_parentheses</span></span>

|<span data-ttu-id="d8f73-399">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-399">Property</span></span>|<span data-ttu-id="d8f73-400">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-400">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-401">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-401">**Option name**</span></span> | <span data-ttu-id="d8f73-402">csharp_space_between_parentheses</span><span class="sxs-lookup"><span data-stu-id="d8f73-402">csharp_space_between_parentheses</span></span> |
| <span data-ttu-id="d8f73-403">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-403">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-404">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-404">C#</span></span> |
| <span data-ttu-id="d8f73-405">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-405">**Introduced version**</span></span> | <span data-ttu-id="d8f73-406">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d8f73-406">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d8f73-407">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-407">**Option values**</span></span> | <span data-ttu-id="d8f73-408">`control_flow_statements` - 제어 흐름 문의 괄호 사이에 공백을 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-408">`control_flow_statements` - Place space between parentheses of control flow statements</span></span><br /><br /><span data-ttu-id="d8f73-409">`expressions` - 식의 괄호 사이에 공백을 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-409">`expressions` - Place space between parentheses of expressions</span></span><br /><br /><span data-ttu-id="d8f73-410">`type_casts` - 형식 캐스트의 괄호 사이에 공백을 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-410">`type_casts` - Place space between parentheses in type casts</span></span> |

<span data-ttu-id="d8f73-411">이 규칙을 생략하거나 `control_flow_statements`, `expressions` 또는 `type_casts` 이외의 값을 사용하면 설정이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-411">If you omit this rule or use a value other than `control_flow_statements`, `expressions`, or `type_casts`, the setting is not applied.</span></span>

<span data-ttu-id="d8f73-412">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-412">Code examples:</span></span>

```csharp
// csharp_space_between_parentheses = control_flow_statements
for ( int i = 0; i < 10; i++ ) { }

// csharp_space_between_parentheses = expressions
var z = ( x * y ) - ( ( y - x ) * 3 );

// csharp_space_between_parentheses = type_casts
int y = ( int )x;
```

#### <a name="csharp_space_before_colon_in_inheritance_clause"></a><span data-ttu-id="d8f73-413">csharp\_space\_before\_colon\_in\_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="d8f73-413">csharp\_space\_before\_colon\_in\_inheritance_clause</span></span>

|<span data-ttu-id="d8f73-414">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-414">Property</span></span>|<span data-ttu-id="d8f73-415">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-415">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-416">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-416">**Option name**</span></span> | <span data-ttu-id="d8f73-417">csharp_space_before_colon_in_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="d8f73-417">csharp_space_before_colon_in_inheritance_clause</span></span> |
| <span data-ttu-id="d8f73-418">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-418">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-419">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-419">C#</span></span> |
| <span data-ttu-id="d8f73-420">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-420">**Introduced version**</span></span> | <span data-ttu-id="d8f73-421">Visual Studio 2017 버전 15.7</span><span class="sxs-lookup"><span data-stu-id="d8f73-421">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="d8f73-422">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-422">**Option values**</span></span> | <span data-ttu-id="d8f73-423">`true` - 형식 선언에서 베이스 또는 인터페이스의 콜론 앞에 공백 문자를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-423">`true` - Place a space character before the colon for bases or interfaces in a type declaration</span></span><br /><br /><span data-ttu-id="d8f73-424">`false` - 형식 선언에서 베이스 또는 인터페이스의 콜론 앞에서 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-424">`false` - Remove space before the colon for bases or interfaces in a type declaration</span></span> |

<span data-ttu-id="d8f73-425">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-425">Code examples:</span></span>

```csharp
// csharp_space_before_colon_in_inheritance_clause = true
interface I
{

}

class C : I
{

}

// csharp_space_before_colon_in_inheritance_clause = false
interface I
{

}

class C: I
{

}
```

#### <a name="csharp_space_after_colon_in_inheritance_clause"></a><span data-ttu-id="d8f73-426">csharp\_space\_after\_colon\_in\_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="d8f73-426">csharp\_space\_after\_colon\_in\_inheritance_clause</span></span>

|<span data-ttu-id="d8f73-427">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-427">Property</span></span>|<span data-ttu-id="d8f73-428">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-428">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-429">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-429">**Option name**</span></span> | <span data-ttu-id="d8f73-430">csharp_space_after_colon_in_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="d8f73-430">csharp_space_after_colon_in_inheritance_clause</span></span> |
| <span data-ttu-id="d8f73-431">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-431">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-432">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-432">C#</span></span> |
| <span data-ttu-id="d8f73-433">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-433">**Introduced version**</span></span> | <span data-ttu-id="d8f73-434">Visual Studio 2017 버전 15.7</span><span class="sxs-lookup"><span data-stu-id="d8f73-434">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="d8f73-435">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-435">**Option values**</span></span> | <span data-ttu-id="d8f73-436">`true` - 형식 선언에서 베이스 또는 인터페이스의 콜론 뒤에 공백 문자를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-436">`true` - Place a space character after the colon for bases or interfaces in a type declaration</span></span><br /><br /><span data-ttu-id="d8f73-437">`false` - 형식 선언에서 베이스 또는 인터페이스의 콜론 뒤에서 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-437">`false` - Remove space after the colon for bases or interfaces in a type declaration</span></span> |

<span data-ttu-id="d8f73-438">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-438">Code examples:</span></span>

```csharp
// csharp_space_after_colon_in_inheritance_clause = true
interface I
{

}

class C : I
{

}

// csharp_space_after_colon_in_inheritance_clause = false
interface I
{

}

class C :I
{

}
```

#### <a name="csharp_space_around_binary_operators"></a><span data-ttu-id="d8f73-439">csharp\_space\_around\_binary_operators</span><span class="sxs-lookup"><span data-stu-id="d8f73-439">csharp\_space\_around\_binary_operators</span></span>

|<span data-ttu-id="d8f73-440">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-440">Property</span></span>|<span data-ttu-id="d8f73-441">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-441">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-442">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-442">**Option name**</span></span> | <span data-ttu-id="d8f73-443">csharp_space_around_binary_operators</span><span class="sxs-lookup"><span data-stu-id="d8f73-443">csharp_space_around_binary_operators</span></span> |
| <span data-ttu-id="d8f73-444">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-444">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-445">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-445">C#</span></span> |
| <span data-ttu-id="d8f73-446">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-446">**Introduced version**</span></span> | <span data-ttu-id="d8f73-447">Visual Studio 2017 버전 15.7</span><span class="sxs-lookup"><span data-stu-id="d8f73-447">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="d8f73-448">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-448">**Option values**</span></span> | <span data-ttu-id="d8f73-449">`before_and_after` - 이항 연산자 앞뒤에 공백을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-449">`before_and_after` - Insert space before and after the binary operator</span></span><br /><br /><span data-ttu-id="d8f73-450">`none` - 이항 연산자 앞뒤의 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-450">`none` - Remove spaces before and after the binary operator</span></span><br /><br /><span data-ttu-id="d8f73-451">`ignore` - 이항 연산자 주위의 공백을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-451">`ignore` - Ignore spaces around binary operators</span></span> |

<span data-ttu-id="d8f73-452">이 규칙을 생략하거나 `before_and_after`, `none` 또는 `ignore` 이외의 값을 사용하는 경우 설정이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-452">If you omit this rule, or use a value other than `before_and_after`, `none`, or `ignore`, the setting is not applied.</span></span>

<span data-ttu-id="d8f73-453">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-453">Code examples:</span></span>

```csharp
// csharp_space_around_binary_operators = before_and_after
return x * (x - y);

// csharp_space_around_binary_operators = none
return x*(x-y);

// csharp_space_around_binary_operators = ignore
return x  *  (x-y);
```

#### <a name="csharp_space_between_method_declaration_parameter_list_parentheses"></a><span data-ttu-id="d8f73-454">csharp_space_between_method_declaration_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="d8f73-454">csharp_space_between_method_declaration_parameter_list_parentheses</span></span>

|<span data-ttu-id="d8f73-455">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-455">Property</span></span>|<span data-ttu-id="d8f73-456">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-456">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-457">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-457">**Option name**</span></span> | <span data-ttu-id="d8f73-458">csharp_space_between_method_declaration_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="d8f73-458">csharp_space_between_method_declaration_parameter_list_parentheses</span></span> |
| <span data-ttu-id="d8f73-459">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-459">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-460">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-460">C#</span></span> |
| <span data-ttu-id="d8f73-461">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-461">**Introduced version**</span></span> | <span data-ttu-id="d8f73-462">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d8f73-462">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d8f73-463">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-463">**Option values**</span></span> | <span data-ttu-id="d8f73-464">`true` - 여는 괄호 뒤 및 메서드 선언 매개 변수 목록의 닫는 괄호 앞에 공백 문자를 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-464">`true` - Place a space character after the opening parenthesis and before the closing parenthesis of a method declaration parameter list</span></span><br /><br /><span data-ttu-id="d8f73-465">`false` - 여는 괄호 뒤 및 메서드 선언 매개 변수 목록의 닫는 괄호 앞에서 공백 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-465">`false` - Remove space characters after the opening parenthesis and before the closing parenthesis of a method declaration parameter list</span></span> |

<span data-ttu-id="d8f73-466">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-466">Code examples:</span></span>

```csharp
// csharp_space_between_method_declaration_parameter_list_parentheses = true
void Bark( int x ) { ... }

// csharp_space_between_method_declaration_parameter_list_parentheses = false
void Bark(int x) { ... }
```

#### <a name="csharp_space_between_method_declaration_empty_parameter_list_parentheses"></a><span data-ttu-id="d8f73-467">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="d8f73-467">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span></span>

|<span data-ttu-id="d8f73-468">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-468">Property</span></span>|<span data-ttu-id="d8f73-469">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-469">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-470">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-470">**Option name**</span></span> | <span data-ttu-id="d8f73-471">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="d8f73-471">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span></span> |
| <span data-ttu-id="d8f73-472">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-472">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-473">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-473">C#</span></span> |
| <span data-ttu-id="d8f73-474">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-474">**Introduced version**</span></span> | <span data-ttu-id="d8f73-475">Visual Studio 2017 버전 15.7</span><span class="sxs-lookup"><span data-stu-id="d8f73-475">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="d8f73-476">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-476">**Option values**</span></span> | <span data-ttu-id="d8f73-477">`true` - 메서드 선언에서 빈 매개 변수 목록 괄호 안에 공백을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-477">`true` - Insert space within empty parameter list parentheses for a method declaration</span></span><br /><br /><span data-ttu-id="d8f73-478">`false` - 메서드 선언에서 빈 매개 변수 목록 괄호 안의 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-478">`false` - Remove space within empty parameter list parentheses for a method declaration</span></span> |

<span data-ttu-id="d8f73-479">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-479">Code examples:</span></span>

```csharp
// csharp_space_between_method_declaration_empty_parameter_list_parentheses = true
void Goo( )
{
    Goo(1);
}

void Goo(int x)
{
    Goo();
}

// csharp_space_between_method_declaration_empty_parameter_list_parentheses = false
void Goo()
{
    Goo(1);
}

void Goo(int x)
{
    Goo();
}
```

#### <a name="csharp_space_between_method_declaration_name_and_open_parenthesis"></a><span data-ttu-id="d8f73-480">csharp_space_between_method_declaration_name_and_open_parenthesis</span><span class="sxs-lookup"><span data-stu-id="d8f73-480">csharp_space_between_method_declaration_name_and_open_parenthesis</span></span>

|<span data-ttu-id="d8f73-481">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-481">Property</span></span>|<span data-ttu-id="d8f73-482">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-482">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-483">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-483">**Option name**</span></span> | <span data-ttu-id="d8f73-484">csharp_space_between_method_declaration_name_and_open_parenthesis</span><span class="sxs-lookup"><span data-stu-id="d8f73-484">csharp_space_between_method_declaration_name_and_open_parenthesis</span></span> |
| <span data-ttu-id="d8f73-485">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-485">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-486">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-486">C#</span></span> |
| <span data-ttu-id="d8f73-487">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-487">**Option values**</span></span> | <span data-ttu-id="d8f73-488">`true` -메서드 선언에서 메서드 이름과 여는 괄호 사이에 공백 문자를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-488">`true` - Place a space character between the method name and opening parenthesis in the method declaration</span></span><br /><br /><span data-ttu-id="d8f73-489">`false` -메서드 선언에서 메서드 이름과 여는 괄호 사이에서 공백 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-489">`false` - Remove space characters between the method name and opening parenthesis in the method declaration</span></span> |

<span data-ttu-id="d8f73-490">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-490">Code examples:</span></span>

```csharp
// csharp_space_between_method_declaration_name_and_open_parenthesis = true
void M () { }

// csharp_space_between_method_declaration_name_and_open_parenthesis = false
void M() { }
```

#### <a name="csharp_space_between_method_call_parameter_list_parentheses"></a><span data-ttu-id="d8f73-491">csharp_space_between_method_call_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="d8f73-491">csharp_space_between_method_call_parameter_list_parentheses</span></span>

|<span data-ttu-id="d8f73-492">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-492">Property</span></span>|<span data-ttu-id="d8f73-493">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-493">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-494">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-494">**Option name**</span></span> | <span data-ttu-id="d8f73-495">csharp_space_between_method_call_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="d8f73-495">csharp_space_between_method_call_parameter_list_parentheses</span></span> |
| <span data-ttu-id="d8f73-496">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-496">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-497">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-497">C#</span></span> |
| <span data-ttu-id="d8f73-498">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-498">**Introduced version**</span></span> | <span data-ttu-id="d8f73-499">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d8f73-499">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d8f73-500">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-500">**Option values**</span></span> | <span data-ttu-id="d8f73-501">`true` - 여는 괄호 뒤 및 메서드 호출의 닫는 괄호 앞에 공백 문자를 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-501">`true` - Place a space character after the opening parenthesis and before the closing parenthesis of a method call</span></span><br /><br /><span data-ttu-id="d8f73-502">`false` - 여는 괄호 뒤 및 메서드 호출의 닫는 괄호 앞에서 공백 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-502">`false` - Remove space characters after the opening parenthesis and before the closing parenthesis of a method call</span></span> |

<span data-ttu-id="d8f73-503">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-503">Code examples:</span></span>

```csharp
// csharp_space_between_method_call_parameter_list_parentheses = true
MyMethod( argument );

// csharp_space_between_method_call_parameter_list_parentheses = false
MyMethod(argument);
```

#### <a name="csharp_space_between_method_call_empty_parameter_list_parentheses"></a><span data-ttu-id="d8f73-504">csharp_space_between_method_call_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="d8f73-504">csharp_space_between_method_call_empty_parameter_list_parentheses</span></span>

|<span data-ttu-id="d8f73-505">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-505">Property</span></span>|<span data-ttu-id="d8f73-506">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-506">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-507">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-507">**Option name**</span></span> | <span data-ttu-id="d8f73-508">csharp_space_between_method_call_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="d8f73-508">csharp_space_between_method_call_empty_parameter_list_parentheses</span></span> |
| <span data-ttu-id="d8f73-509">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-509">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-510">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-510">C#</span></span> |
| <span data-ttu-id="d8f73-511">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-511">**Introduced version**</span></span> | <span data-ttu-id="d8f73-512">Visual Studio 2017 버전 15.7</span><span class="sxs-lookup"><span data-stu-id="d8f73-512">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="d8f73-513">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-513">**Option values**</span></span> | <span data-ttu-id="d8f73-514">`true` - 빈 인수 목록 괄호 안에 공백을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-514">`true` - Insert space within empty argument list parentheses</span></span><br /><br /><span data-ttu-id="d8f73-515">`false` - 빈 인수 목록 괄호 안의 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-515">`false` - Remove space within empty argument list parentheses</span></span> |

<span data-ttu-id="d8f73-516">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-516">Code examples:</span></span>

```csharp
// csharp_space_between_method_call_empty_parameter_list_parentheses = true
void Goo()
{
    Goo(1);
}

void Goo(int x)
{
    Goo( );
}

// csharp_space_between_method_call_empty_parameter_list_parentheses = false
void Goo()
{
    Goo(1);
}

void Goo(int x)
{
    Goo();
}
```

#### <a name="csharp_space_between_method_call_name_and_opening_parenthesis"></a><span data-ttu-id="d8f73-517">csharp_space_between_method_call_name_and_opening_parenthesis</span><span class="sxs-lookup"><span data-stu-id="d8f73-517">csharp_space_between_method_call_name_and_opening_parenthesis</span></span>

|<span data-ttu-id="d8f73-518">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-518">Property</span></span>|<span data-ttu-id="d8f73-519">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-519">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-520">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-520">**Option name**</span></span> | <span data-ttu-id="d8f73-521">csharp_space_between_method_call_name_and_opening_parenthesis</span><span class="sxs-lookup"><span data-stu-id="d8f73-521">csharp_space_between_method_call_name_and_opening_parenthesis</span></span> |
| <span data-ttu-id="d8f73-522">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-522">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-523">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-523">C#</span></span> |
| <span data-ttu-id="d8f73-524">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-524">**Introduced version**</span></span> | <span data-ttu-id="d8f73-525">Visual Studio 2017 버전 15.7</span><span class="sxs-lookup"><span data-stu-id="d8f73-525">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="d8f73-526">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-526">**Option values**</span></span> | <span data-ttu-id="d8f73-527">`true` - 메서드 호출 이름과 여는 괄호 사이에 공백을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-527">`true` - Insert space between method call name and opening parenthesis</span></span><br /><br /><span data-ttu-id="d8f73-528">`false` - 메서드 호출 이름과 여는 괄호 사이의 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-528">`false` - Remove space between method call name and opening parenthesis</span></span> |

<span data-ttu-id="d8f73-529">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-529">Code examples:</span></span>

```csharp
// csharp_space_between_method_call_name_and_opening_parenthesis = true
void Goo()
{
    Goo (1);
}

void Goo(int x)
{
    Goo ();
}

// csharp_space_between_method_call_name_and_opening_parenthesis = false
void Goo()
{
    Goo(1);
}

void Goo(int x)
{
    Goo();
}
```

#### <a name="csharp_space_after_comma"></a><span data-ttu-id="d8f73-530">csharp_space_after_comma</span><span class="sxs-lookup"><span data-stu-id="d8f73-530">csharp_space_after_comma</span></span>

|<span data-ttu-id="d8f73-531">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-531">Property</span></span>|<span data-ttu-id="d8f73-532">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-532">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-533">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-533">**Option name**</span></span> | <span data-ttu-id="d8f73-534">csharp_space_after_comma</span><span class="sxs-lookup"><span data-stu-id="d8f73-534">csharp_space_after_comma</span></span> |
| <span data-ttu-id="d8f73-535">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-535">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-536">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-536">C#</span></span> |
| <span data-ttu-id="d8f73-537">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-537">**Option values**</span></span> | <span data-ttu-id="d8f73-538">`true` - 쉼표 뒤에 공백을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-538">`true` - Insert space after a comma</span></span><br /><br /><span data-ttu-id="d8f73-539">`false` - 쉼표 뒤의 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-539">`false` - Remove space after a comma</span></span> |

<span data-ttu-id="d8f73-540">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-540">Code examples:</span></span>

```csharp
// csharp_space_after_comma = true
int[] x = new int[] { 1, 2, 3, 4, 5 };

// csharp_space_after_comma = false
int[] x = new int[] { 1,2,3,4,5 }
```

#### <a name="csharp_space_before_comma"></a><span data-ttu-id="d8f73-541">csharp_space_before_comma</span><span class="sxs-lookup"><span data-stu-id="d8f73-541">csharp_space_before_comma</span></span>

|<span data-ttu-id="d8f73-542">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-542">Property</span></span>|<span data-ttu-id="d8f73-543">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-543">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-544">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-544">**Option name**</span></span> | <span data-ttu-id="d8f73-545">csharp_space_before_comma</span><span class="sxs-lookup"><span data-stu-id="d8f73-545">csharp_space_before_comma</span></span> |
| <span data-ttu-id="d8f73-546">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-546">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-547">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-547">C#</span></span> |
| <span data-ttu-id="d8f73-548">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-548">**Option values**</span></span> | <span data-ttu-id="d8f73-549">`true` - 쉼표 앞에 공백을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-549">`true` - Insert space before a comma</span></span><br /><br /><span data-ttu-id="d8f73-550">`false` - 쉼표 앞에서 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-550">`false` - Remove space before a comma</span></span> |

<span data-ttu-id="d8f73-551">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-551">Code examples:</span></span>

```csharp
// csharp_space_before_comma = true
int[] x = new int[] { 1 , 2 , 3 , 4 , 5 };

// csharp_space_before_comma = false
int[] x = new int[] { 1, 2, 3, 4, 5 };
```

#### <a name="csharp_space_after_dot"></a><span data-ttu-id="d8f73-552">csharp_space_after_dot</span><span class="sxs-lookup"><span data-stu-id="d8f73-552">csharp_space_after_dot</span></span>

|<span data-ttu-id="d8f73-553">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-553">Property</span></span>|<span data-ttu-id="d8f73-554">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-554">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-555">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-555">**Option name**</span></span> | <span data-ttu-id="d8f73-556">csharp_space_after_dot</span><span class="sxs-lookup"><span data-stu-id="d8f73-556">csharp_space_after_dot</span></span> |
| <span data-ttu-id="d8f73-557">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-557">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-558">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-558">C#</span></span> |
| <span data-ttu-id="d8f73-559">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-559">**Option values**</span></span> | <span data-ttu-id="d8f73-560">`true` - 점 뒤에 공백을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-560">`true` - Insert space after a dot</span></span><br /><br /><span data-ttu-id="d8f73-561">`false` - 점 뒤의 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-561">`false` - Remove space after a dot</span></span> |

<span data-ttu-id="d8f73-562">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-562">Code examples:</span></span>

```csharp
// csharp_space_after_dot = true
this. Goo();

// csharp_space_after_dot = false
this.Goo();
```

#### <a name="csharp_space_before_dot"></a><span data-ttu-id="d8f73-563">csharp_space_before_dot</span><span class="sxs-lookup"><span data-stu-id="d8f73-563">csharp_space_before_dot</span></span>

|<span data-ttu-id="d8f73-564">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-564">Property</span></span>|<span data-ttu-id="d8f73-565">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-565">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-566">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-566">**Option name**</span></span> | <span data-ttu-id="d8f73-567">csharp_space_before_dot</span><span class="sxs-lookup"><span data-stu-id="d8f73-567">csharp_space_before_dot</span></span> |
| <span data-ttu-id="d8f73-568">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-568">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-569">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-569">C#</span></span> |
| <span data-ttu-id="d8f73-570">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-570">**Option values**</span></span> | <span data-ttu-id="d8f73-571">`true` - 점 앞에 공백을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-571">`true` - Insert space before a dot</span></span> <br /><br /><span data-ttu-id="d8f73-572">`false` - 점 앞에서 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-572">`false` - Remove space before a dot</span></span> |

<span data-ttu-id="d8f73-573">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-573">Code examples:</span></span>

```csharp
// csharp_space_before_dot = true
this .Goo();

// csharp_space_before_dot = false
this.Goo();
```

#### <a name="csharp_space_after_semicolon_in_for_statement"></a><span data-ttu-id="d8f73-574">csharp_space_after_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="d8f73-574">csharp_space_after_semicolon_in_for_statement</span></span>

|<span data-ttu-id="d8f73-575">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-575">Property</span></span>|<span data-ttu-id="d8f73-576">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-576">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-577">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-577">**Option name**</span></span> | <span data-ttu-id="d8f73-578">csharp_space_after_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="d8f73-578">csharp_space_after_semicolon_in_for_statement</span></span> |
| <span data-ttu-id="d8f73-579">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-579">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-580">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-580">C#</span></span> |
| <span data-ttu-id="d8f73-581">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-581">**Option values**</span></span> | <span data-ttu-id="d8f73-582">`true` - `for` 문의 각 세미콜론 뒤에 공백을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-582">`true` - Insert space after each semicolon in a `for` statement</span></span><br /><br /><span data-ttu-id="d8f73-583">`false` - `for` 문의 각 세미콜론 뒤에서 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-583">`false` - Remove space after each semicolon in a `for` statement</span></span> |

<span data-ttu-id="d8f73-584">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-584">Code examples:</span></span>

```csharp
// csharp_space_after_semicolon_in_for_statement = true
for (int i = 0; i < x.Length; i++)

// csharp_space_after_semicolon_in_for_statement = false
for (int i = 0;i < x.Length;i++)
```

#### <a name="csharp_space_before_semicolon_in_for_statement"></a><span data-ttu-id="d8f73-585">csharp_space_before_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="d8f73-585">csharp_space_before_semicolon_in_for_statement</span></span>

|<span data-ttu-id="d8f73-586">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-586">Property</span></span>|<span data-ttu-id="d8f73-587">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-587">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-588">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-588">**Option name**</span></span> | <span data-ttu-id="d8f73-589">csharp_space_before_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="d8f73-589">csharp_space_before_semicolon_in_for_statement</span></span> |
| <span data-ttu-id="d8f73-590">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-590">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-591">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-591">C#</span></span> |
| <span data-ttu-id="d8f73-592">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-592">**Option values**</span></span> | <span data-ttu-id="d8f73-593">`true` - `for` 문의 각 세미콜론 앞에 공백을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-593">`true` - Insert space before each semicolon in a `for` statement</span></span> <br /><br /><span data-ttu-id="d8f73-594">`false` - `for` 문의 각 세미콜론 앞에서 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-594">`false` - Remove space before each semicolon in a `for` statement</span></span> |

<span data-ttu-id="d8f73-595">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-595">Code examples:</span></span>

```csharp
// csharp_space_before_semicolon_in_for_statement = true
for (int i = 0 ; i < x.Length ; i++)

// csharp_space_before_semicolon_in_for_statement = false
for (int i = 0; i < x.Length; i++)
```

#### <a name="csharp_space_around_declaration_statements"></a><span data-ttu-id="d8f73-596">csharp_space_around_declaration_statements</span><span class="sxs-lookup"><span data-stu-id="d8f73-596">csharp_space_around_declaration_statements</span></span>

|<span data-ttu-id="d8f73-597">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-597">Property</span></span>|<span data-ttu-id="d8f73-598">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-598">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-599">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-599">**Option name**</span></span> | <span data-ttu-id="d8f73-600">csharp_space_around_declaration_statements</span><span class="sxs-lookup"><span data-stu-id="d8f73-600">csharp_space_around_declaration_statements</span></span> |
| <span data-ttu-id="d8f73-601">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-601">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-602">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-602">C#</span></span> |
| <span data-ttu-id="d8f73-603">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-603">**Option values**</span></span> | <span data-ttu-id="d8f73-604">`ignore` - 선언문에서 추가 공백 문자를 제거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-604">`ignore` - Don't remove extra space characters in declaration statements</span></span><br /><br /><span data-ttu-id="d8f73-605">`false` - 선언문에서 추가 공백 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-605">`false` - Remove extra space characters in declaration statements</span></span> |

<span data-ttu-id="d8f73-606">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-606">Code examples:</span></span>

```csharp
// csharp_space_around_declaration_statements = ignore
int    x    =    0   ;

// csharp_space_around_declaration_statements = false
int x = 0;
```

#### <a name="csharp_space_before_open_square_brackets"></a><span data-ttu-id="d8f73-607">csharp_space_before_open_square_brackets</span><span class="sxs-lookup"><span data-stu-id="d8f73-607">csharp_space_before_open_square_brackets</span></span>

|<span data-ttu-id="d8f73-608">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-608">Property</span></span>|<span data-ttu-id="d8f73-609">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-609">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-610">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-610">**Option name**</span></span> | <span data-ttu-id="d8f73-611">csharp_space_before_open_square_brackets</span><span class="sxs-lookup"><span data-stu-id="d8f73-611">csharp_space_before_open_square_brackets</span></span> |
| <span data-ttu-id="d8f73-612">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-612">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-613">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-613">C#</span></span> |
| <span data-ttu-id="d8f73-614">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-614">**Option values**</span></span> | <span data-ttu-id="d8f73-615">`true` - 여는 대괄호 `[` 앞에 공백을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-615">`true` - Insert space before opening square brackets `[`</span></span> <br /><br /><span data-ttu-id="d8f73-616">`false` - 여는 대괄호 `[` 앞에서 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-616">`false` - Remove space before opening square brackets `[`</span></span> |

<span data-ttu-id="d8f73-617">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-617">Code examples:</span></span>

```csharp
// csharp_space_before_open_square_brackets = true
int [] numbers = new int [] { 1, 2, 3, 4, 5 };

// csharp_space_before_open_square_brackets = false
int[] numbers = new int[] { 1, 2, 3, 4, 5 };
```

#### <a name="csharp_space_between_empty_square_brackets"></a><span data-ttu-id="d8f73-618">csharp_space_between_empty_square_brackets</span><span class="sxs-lookup"><span data-stu-id="d8f73-618">csharp_space_between_empty_square_brackets</span></span>

|<span data-ttu-id="d8f73-619">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-619">Property</span></span>|<span data-ttu-id="d8f73-620">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-620">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-621">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-621">**Option name**</span></span> | <span data-ttu-id="d8f73-622">csharp_space_between_empty_square_brackets</span><span class="sxs-lookup"><span data-stu-id="d8f73-622">csharp_space_between_empty_square_brackets</span></span> |
| <span data-ttu-id="d8f73-623">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-623">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-624">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-624">C#</span></span> |
| <span data-ttu-id="d8f73-625">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-625">**Option values**</span></span> | <span data-ttu-id="d8f73-626">`true` - 빈 대괄호 `[ ]` 사이에 공백을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-626">`true` - Insert space between empty square brackets `[ ]`</span></span> <br /><br /><span data-ttu-id="d8f73-627">`false` - 빈 대괄호 `[]` 사이에서 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-627">`false` - Remove space between empty square brackets `[]`</span></span> |

<span data-ttu-id="d8f73-628">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-628">Code examples:</span></span>

```csharp
// csharp_space_between_empty_square_brackets = true
int[ ] numbers = new int[ ] { 1, 2, 3, 4, 5 };

// csharp_space_between_empty_square_brackets = false
int[] numbers = new int[] { 1, 2, 3, 4, 5 };
```

#### <a name="csharp_space_between_square_brackets"></a><span data-ttu-id="d8f73-629">csharp_space_between_square_brackets</span><span class="sxs-lookup"><span data-stu-id="d8f73-629">csharp_space_between_square_brackets</span></span>

|<span data-ttu-id="d8f73-630">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-630">Property</span></span>|<span data-ttu-id="d8f73-631">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-631">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-632">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-632">**Option name**</span></span> | <span data-ttu-id="d8f73-633">csharp_space_between_square_brackets</span><span class="sxs-lookup"><span data-stu-id="d8f73-633">csharp_space_between_square_brackets</span></span> |
| <span data-ttu-id="d8f73-634">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-634">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-635">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-635">C#</span></span> |
| <span data-ttu-id="d8f73-636">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-636">**Option values**</span></span> | <span data-ttu-id="d8f73-637">`true` - 비어 있지 않은 대괄호 `[ 0 ]` 안에 공백 문자를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-637">`true` - Insert space characters in non-empty square brackets `[ 0 ]`</span></span> <br /><br /><span data-ttu-id="d8f73-638">`false` - 비어 있지 않은 대괄호 `[0]` 안에서 공백 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-638">`false` - Remove space characters in non-empty square brackets `[0]`</span></span> |

<span data-ttu-id="d8f73-639">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-639">Code examples:</span></span>

```csharp
// csharp_space_between_square_brackets = true
int index = numbers[ 0 ];

// csharp_space_between_square_brackets = false
int index = numbers[0];
```

### <a name="wrap-options"></a><span data-ttu-id="d8f73-640">줄 바꿈 옵션</span><span class="sxs-lookup"><span data-stu-id="d8f73-640">Wrap options</span></span>

<span data-ttu-id="d8f73-641">이러한 서식 설정 규칙은 문 및 코드 블록에 단일 줄 및 별도 줄을 사용하는 것을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-641">These formatting rules concern the use of single lines versus separate lines for statements and code blocks.</span></span>

<span data-ttu-id="d8f73-642">예제 *.editorconfig* 파일:</span><span class="sxs-lookup"><span data-stu-id="d8f73-642">Example *.editorconfig* file:</span></span>

```ini
# CSharp formatting rules:
[*.cs]
csharp_preserve_single_line_statements = true
csharp_preserve_single_line_blocks = true
```

#### <a name="csharp_preserve_single_line_statements"></a><span data-ttu-id="d8f73-643">csharp_preserve_single_line_statements</span><span class="sxs-lookup"><span data-stu-id="d8f73-643">csharp_preserve_single_line_statements</span></span>

|<span data-ttu-id="d8f73-644">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-644">Property</span></span>|<span data-ttu-id="d8f73-645">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-645">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-646">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-646">**Option name**</span></span> | <span data-ttu-id="d8f73-647">csharp_preserve_single_line_statements</span><span class="sxs-lookup"><span data-stu-id="d8f73-647">csharp_preserve_single_line_statements</span></span> |
| <span data-ttu-id="d8f73-648">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-648">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-649">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-649">C#</span></span> |
| <span data-ttu-id="d8f73-650">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-650">**Introduced version**</span></span> | <span data-ttu-id="d8f73-651">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d8f73-651">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d8f73-652">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-652">**Option values**</span></span> | <span data-ttu-id="d8f73-653">`true` - 문과 멤버 선언을 동일한 줄에 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-653">`true` - Leave statements and member declarations on the same line</span></span><br /><br /><span data-ttu-id="d8f73-654">`false` - 문과 멤버 선언을 다른 줄에 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-654">`false` - Leave statements and member declarations on different lines</span></span> |

<span data-ttu-id="d8f73-655">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-655">Code examples:</span></span>

```csharp
//csharp_preserve_single_line_statements = true
int i = 0; string name = "John";

//csharp_preserve_single_line_statements = false
int i = 0;
string name = "John";
```

#### <a name="csharp_preserve_single_line_blocks"></a><span data-ttu-id="d8f73-656">csharp_preserve_single_line_blocks</span><span class="sxs-lookup"><span data-stu-id="d8f73-656">csharp_preserve_single_line_blocks</span></span>

|<span data-ttu-id="d8f73-657">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-657">Property</span></span>|<span data-ttu-id="d8f73-658">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-658">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-659">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-659">**Option name**</span></span> | <span data-ttu-id="d8f73-660">csharp_preserve_single_line_blocks</span><span class="sxs-lookup"><span data-stu-id="d8f73-660">csharp_preserve_single_line_blocks</span></span> |
| <span data-ttu-id="d8f73-661">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-661">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-662">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-662">C#</span></span> |
| <span data-ttu-id="d8f73-663">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-663">**Introduced version**</span></span> | <span data-ttu-id="d8f73-664">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d8f73-664">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d8f73-665">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-665">**Option values**</span></span> | <span data-ttu-id="d8f73-666">`true` - 코드 블록을 한 줄에 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-666">`true` - Leave code block on single line</span></span><br /><br /><span data-ttu-id="d8f73-667">`false` - 코드 블록을 새 줄에 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-667">`false` - Leave code block on separate lines</span></span> |

<span data-ttu-id="d8f73-668">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-668">Code examples:</span></span>

```csharp
//csharp_preserve_single_line_blocks = true
public int Foo { get; set; }

//csharp_preserve_single_line_blocks = false
public int MyProperty
{
    get; set;
}
```

### <a name="using-directive-options"></a><span data-ttu-id="d8f73-669">지시문 옵션 사용</span><span class="sxs-lookup"><span data-stu-id="d8f73-669">Using directive options</span></span>

<span data-ttu-id="d8f73-670">이 서식 지정 규칙은 네임스페이스 내부에 배치거나 외부에 배치되는 지시문을 사용하는 것과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f73-670">This formatting rule concerns the use of using directives being placed inside versus outside a namespace.</span></span>

<span data-ttu-id="d8f73-671">예제 *.editorconfig* 파일:</span><span class="sxs-lookup"><span data-stu-id="d8f73-671">Example *.editorconfig* file:</span></span>

```ini
# 'using' directive preferences
[*.cs]
csharp_using_directive_placement = outside_namespace
csharp_using_directive_placement = inside_namespace
```

#### <a name="csharp_using_directive_placement"></a><span data-ttu-id="d8f73-672">csharp_using_directive_placement</span><span class="sxs-lookup"><span data-stu-id="d8f73-672">csharp_using_directive_placement</span></span>

|<span data-ttu-id="d8f73-673">속성</span><span class="sxs-lookup"><span data-stu-id="d8f73-673">Property</span></span>|<span data-ttu-id="d8f73-674">값</span><span class="sxs-lookup"><span data-stu-id="d8f73-674">Value</span></span>|
|-|-|
| <span data-ttu-id="d8f73-675">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d8f73-675">**Option name**</span></span> | <span data-ttu-id="d8f73-676">csharp_using_directive_placement</span><span class="sxs-lookup"><span data-stu-id="d8f73-676">csharp_using_directive_placement</span></span> |
| <span data-ttu-id="d8f73-677">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d8f73-677">**Applicable languages**</span></span> | <span data-ttu-id="d8f73-678">C#</span><span class="sxs-lookup"><span data-stu-id="d8f73-678">C#</span></span> |
| <span data-ttu-id="d8f73-679">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d8f73-679">**Introduced version**</span></span> | <span data-ttu-id="d8f73-680">Visual Studio 2019 버전 16.1</span><span class="sxs-lookup"><span data-stu-id="d8f73-680">Visual Studio 2019 version 16.1</span></span> |
| <span data-ttu-id="d8f73-681">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d8f73-681">**Option values**</span></span> | <span data-ttu-id="d8f73-682">`outside_namespace` - 네임스페이스 외부에서 지시문을 사용</span><span class="sxs-lookup"><span data-stu-id="d8f73-682">`outside_namespace` - Leave using directives outside namespace</span></span><br /><br /><span data-ttu-id="d8f73-683">`inside_namespace` - 네임스페이스 내부에서 지시문을 사용</span><span class="sxs-lookup"><span data-stu-id="d8f73-683">`inside_namespace` - Leave using directives inside namespace</span></span> |

<span data-ttu-id="d8f73-684">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d8f73-684">Code examples:</span></span>

```csharp
// csharp_using_directive_placement = outside_namespace
using System;

namespace Conventions
{

}

// csharp_using_directive_placement = inside_namespace
namespace Conventions
{
    using System;
}
```

## <a name="see-also"></a><span data-ttu-id="d8f73-685">참조</span><span class="sxs-lookup"><span data-stu-id="d8f73-685">See also</span></span>

- [<span data-ttu-id="d8f73-686">언어 규칙</span><span class="sxs-lookup"><span data-stu-id="d8f73-686">Language rules</span></span>](language-rules.md)
- [<span data-ttu-id="d8f73-687">이름 지정 규칙</span><span class="sxs-lookup"><span data-stu-id="d8f73-687">Naming rules</span></span>](naming-rules.md)
- [<span data-ttu-id="d8f73-688">.NET 코드 스타일 규칙 참조</span><span class="sxs-lookup"><span data-stu-id="d8f73-688">.NET code style rules reference</span></span>](index.md)
