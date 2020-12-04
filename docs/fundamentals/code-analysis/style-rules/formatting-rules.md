---
title: 코드 스타일 서식 지정 규칙
description: 들여쓰기, 공백 및 새 줄의 서식을 지정 하는 코드 스타일 규칙에 대해 알아봅니다.
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
ms.openlocfilehash: 61e6f6a6afdc6aaf9710eef3143af8ae700ef612
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "96593199"
---
# <a name="formatting-rules"></a><span data-ttu-id="d1f54-103">서식 지정 규칙</span><span class="sxs-lookup"><span data-stu-id="d1f54-103">Formatting rules</span></span>

<span data-ttu-id="d1f54-104">서식 지정 규칙은 들여쓰기, 공백 및 새 줄이 .NET 프로그래밍 언어 구문 주위에 정렬 되는 방식에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-104">Formatting rules affect how indentation, spaces, and new lines are aligned around .NET programming language constructs.</span></span> <span data-ttu-id="d1f54-105">규칙은 다음과 같은 범주로 분류 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-105">The rules fall into the following categories:</span></span>

- <span data-ttu-id="d1f54-106">[.Net 서식 지정 규칙](#net-formatting-rules): c # 및 Visual Basic 모두에 적용 되는 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-106">[.NET formatting rules](#net-formatting-rules): Rules that apply to both C# and Visual Basic.</span></span> <span data-ttu-id="d1f54-107">이러한 규칙에 대 한 EditorConfig 옵션 이름은 접두사로 시작 합니다 `dotnet_` .</span><span class="sxs-lookup"><span data-stu-id="d1f54-107">The EditorConfig option names for these rules start with `dotnet_` prefix.</span></span>
- <span data-ttu-id="d1f54-108">[C # 서식 지정 규칙](#c-formatting-rules): c # 언어에만 적용 되는 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-108">[C# formatting rules](#c-formatting-rules): Rules that are specific to C# language only.</span></span> <span data-ttu-id="d1f54-109">이러한 규칙에 대 한 EditorConfig 옵션 이름은 접두사로 시작 합니다 `csharp_` .</span><span class="sxs-lookup"><span data-stu-id="d1f54-109">The EditorConfig option names for these rules start with `csharp_` prefix.</span></span>

## <a name="rule-id-ide0055-fix-formatting"></a><span data-ttu-id="d1f54-110">규칙 ID: "IDE0055" (형식 수정)</span><span class="sxs-lookup"><span data-stu-id="d1f54-110">Rule ID: "IDE0055" (Fix formatting)</span></span>

<span data-ttu-id="d1f54-111">모든 서식 옵션에는 규칙 ID `IDE0055` 와 제목이 있습니다 `Fix formatting` .</span><span class="sxs-lookup"><span data-stu-id="d1f54-111">All formatting options have rule ID `IDE0055` and title `Fix formatting`.</span></span> <span data-ttu-id="d1f54-112">다음 구성 줄을 사용 하 여 EditorConfig 파일에서 서식 위반의 심각도를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-112">Set the severity of a formatting violation in an EditorConfig file using the following configuration line.</span></span>

```ini
dotnet_diagnostic.IDE0055.severity = <severity value>
```

<span data-ttu-id="d1f54-113">심각도 값은 `warning` `error` [빌드 시 적용](../overview.md#code-style-analysis)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-113">The severity value must be `warning` or `error` to be [enforced on build](../overview.md#code-style-analysis).</span></span> <span data-ttu-id="d1f54-114">가능한 모든 심각도 값은 [심각도 수준](../configuration-options.md#severity-level)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d1f54-114">For all possible severity values, see [severity level](../configuration-options.md#severity-level).</span></span>

## <a name="option-format"></a><span data-ttu-id="d1f54-115">옵션 형식</span><span class="sxs-lookup"><span data-stu-id="d1f54-115">Option format</span></span>

<span data-ttu-id="d1f54-116">서식 지정 규칙에 대 한 옵션은 다음과 같은 형식의 EditorConfig 파일에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-116">Options for formatting rules can be specified in an EditorConfig file with the following format:</span></span>

`rule_name = value`

<span data-ttu-id="d1f54-117">대부분의 규칙에서, `value`에 대해 `true`(이 스타일 선호) 또는 `false`(이 스타일 선호 안 함)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-117">For many rules, you specify either `true` (prefer this style) or `false` (do not prefer this style) for `value`.</span></span> <span data-ttu-id="d1f54-118">다른 규칙의 경우 `flush_left`, `before_and_after` 등의 값을 지정하여 규칙을 적용할 시기 및 위치를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-118">For other rules, you specify a value such as `flush_left` or `before_and_after` to describe when and where to apply the rule.</span></span> <span data-ttu-id="d1f54-119">심각도를 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-119">You don't specify a severity.</span></span>

## <a name="net-formatting-rules"></a><span data-ttu-id="d1f54-120">.NET 서식 지정 규칙</span><span class="sxs-lookup"><span data-stu-id="d1f54-120">.NET formatting rules</span></span>

<span data-ttu-id="d1f54-121">이 단원의 서식 지정 규칙은 c # 및 Visual Basic에 모두 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-121">The formatting rules in this section apply to both C# and Visual Basic.</span></span>

- [<span data-ttu-id="d1f54-122">using 구성</span><span class="sxs-lookup"><span data-stu-id="d1f54-122">Organize usings</span></span>](#organize-using-directives)
  - <span data-ttu-id="d1f54-123">dotnet_sort_system_directives_first</span><span class="sxs-lookup"><span data-stu-id="d1f54-123">dotnet_sort_system_directives_first</span></span>
  - <span data-ttu-id="d1f54-124">dotnet_separate_import_directive_groups</span><span class="sxs-lookup"><span data-stu-id="d1f54-124">dotnet_separate_import_directive_groups</span></span>

### <a name="organize-using-directives"></a><span data-ttu-id="d1f54-125">using 지시문 구성</span><span class="sxs-lookup"><span data-stu-id="d1f54-125">Organize using directives</span></span>

<span data-ttu-id="d1f54-126">이러한 서식 지정 규칙은 `using` 지시문과 `Imports` 문의 정렬 및 표시를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-126">These formatting rules concern the sorting and display of `using` directives and `Imports` statements.</span></span>

<span data-ttu-id="d1f54-127">예제 *.editorconfig* 파일:</span><span class="sxs-lookup"><span data-stu-id="d1f54-127">Example *.editorconfig* file:</span></span>

```ini
# .NET formatting rules
[*.{cs,vb}]
dotnet_sort_system_directives_first = true
dotnet_separate_import_directive_groups = true
```

#### <a name="dotnet_sort_system_directives_first"></a><span data-ttu-id="d1f54-128">dotnet\_sort\_system\_directives_first</span><span class="sxs-lookup"><span data-stu-id="d1f54-128">dotnet\_sort\_system\_directives_first</span></span>

|<span data-ttu-id="d1f54-129">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-129">Property</span></span>|<span data-ttu-id="d1f54-130">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-130">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-131">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-131">**Option name**</span></span> | <span data-ttu-id="d1f54-132">dotnet_sort_system_directives_first</span><span class="sxs-lookup"><span data-stu-id="d1f54-132">dotnet_sort_system_directives_first</span></span> |
| <span data-ttu-id="d1f54-133">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-133">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-134">C# 및 Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d1f54-134">C# and Visual Basic</span></span> |
| <span data-ttu-id="d1f54-135">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-135">**Introduced version**</span></span> | <span data-ttu-id="d1f54-136">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d1f54-136">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d1f54-137">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-137">**Option values**</span></span> | <span data-ttu-id="d1f54-138">`true` - `System.*` `using` 지시문을 사전순으로 정렬 하 고 다른 using 지시문 앞에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-138">`true` - Sort `System.*` `using` directives alphabetically, and place them before other using directives.</span></span><br /><br /><span data-ttu-id="d1f54-139">`false` - `System.*` `using` 다른 지시문 앞에 지시문을 추가 하지 않습니다 `using` .</span><span class="sxs-lookup"><span data-stu-id="d1f54-139">`false` - Do not place `System.*` `using` directives before other `using` directives.</span></span> |

<span data-ttu-id="d1f54-140">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-140">Code examples:</span></span>

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

#### <a name="dotnet_separate_import_directive_groups"></a><span data-ttu-id="d1f54-141">dotnet\_separate\_import\_directive\_groups</span><span class="sxs-lookup"><span data-stu-id="d1f54-141">dotnet\_separate\_import\_directive\_groups</span></span>

|<span data-ttu-id="d1f54-142">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-142">Property</span></span>|<span data-ttu-id="d1f54-143">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-143">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-144">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-144">**Option name**</span></span> | <span data-ttu-id="d1f54-145">dotnet_separate_import_directive_groups</span><span class="sxs-lookup"><span data-stu-id="d1f54-145">dotnet_separate_import_directive_groups</span></span> |
| <span data-ttu-id="d1f54-146">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-146">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-147">C# 및 Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d1f54-147">C# and Visual Basic</span></span> |
| <span data-ttu-id="d1f54-148">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-148">**Introduced version**</span></span> | <span data-ttu-id="d1f54-149">Visual Studio 2017 15.5 버전</span><span class="sxs-lookup"><span data-stu-id="d1f54-149">Visual Studio 2017 version 15.5</span></span> |
| <span data-ttu-id="d1f54-150">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-150">**Option values**</span></span> | <span data-ttu-id="d1f54-151">`true` - `using` 지시문 그룹 사이에 빈 줄을 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-151">`true` - Place a blank line between `using` directive groups.</span></span><br /><br /><span data-ttu-id="d1f54-152">`false` - `using` 지시문 그룹 사이에 빈 줄을 넣지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-152">`false` - Do not place a blank line between `using` directive groups.</span></span> |

<span data-ttu-id="d1f54-153">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-153">Code examples:</span></span>

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

## <a name="c-formatting-rules"></a><span data-ttu-id="d1f54-154">C # 서식 지정 규칙</span><span class="sxs-lookup"><span data-stu-id="d1f54-154">C# formatting rules</span></span>

<span data-ttu-id="d1f54-155">이 섹션의 서식 설정 규칙은 C# 코드에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-155">The formatting rules in this section apply only to C# code.</span></span>

- [<span data-ttu-id="d1f54-156">줄 바꿈 옵션</span><span class="sxs-lookup"><span data-stu-id="d1f54-156">Newline options</span></span>](#new-line-options)
  - <span data-ttu-id="d1f54-157">csharp_new_line_before_open_brace</span><span class="sxs-lookup"><span data-stu-id="d1f54-157">csharp_new_line_before_open_brace</span></span>
  - <span data-ttu-id="d1f54-158">csharp_new_line_before_else</span><span class="sxs-lookup"><span data-stu-id="d1f54-158">csharp_new_line_before_else</span></span>
  - <span data-ttu-id="d1f54-159">csharp_new_line_before_catch</span><span class="sxs-lookup"><span data-stu-id="d1f54-159">csharp_new_line_before_catch</span></span>
  - <span data-ttu-id="d1f54-160">csharp_new_line_before_finally</span><span class="sxs-lookup"><span data-stu-id="d1f54-160">csharp_new_line_before_finally</span></span>
  - <span data-ttu-id="d1f54-161">csharp_new_line_before_members_in_object_initializers</span><span class="sxs-lookup"><span data-stu-id="d1f54-161">csharp_new_line_before_members_in_object_initializers</span></span>
  - <span data-ttu-id="d1f54-162">csharp_new_line_before_members_in_anonymous_types</span><span class="sxs-lookup"><span data-stu-id="d1f54-162">csharp_new_line_before_members_in_anonymous_types</span></span>
  - <span data-ttu-id="d1f54-163">csharp_new_line_between_query_expression_clauses</span><span class="sxs-lookup"><span data-stu-id="d1f54-163">csharp_new_line_between_query_expression_clauses</span></span>
- [<span data-ttu-id="d1f54-164">들여쓰기 옵션</span><span class="sxs-lookup"><span data-stu-id="d1f54-164">Indentation options</span></span>](#indentation-options)
  - <span data-ttu-id="d1f54-165">csharp_indent_case_contents</span><span class="sxs-lookup"><span data-stu-id="d1f54-165">csharp_indent_case_contents</span></span>
  - <span data-ttu-id="d1f54-166">csharp_indent_switch_labels</span><span class="sxs-lookup"><span data-stu-id="d1f54-166">csharp_indent_switch_labels</span></span>
  - <span data-ttu-id="d1f54-167">csharp_indent_labels</span><span class="sxs-lookup"><span data-stu-id="d1f54-167">csharp_indent_labels</span></span>
  - <span data-ttu-id="d1f54-168">csharp_indent_block_contents</span><span class="sxs-lookup"><span data-stu-id="d1f54-168">csharp_indent_block_contents</span></span>
  - <span data-ttu-id="d1f54-169">csharp_indent_braces</span><span class="sxs-lookup"><span data-stu-id="d1f54-169">csharp_indent_braces</span></span>
  - <span data-ttu-id="d1f54-170">csharp_indent_case_contents_when_block</span><span class="sxs-lookup"><span data-stu-id="d1f54-170">csharp_indent_case_contents_when_block</span></span>
- [<span data-ttu-id="d1f54-171">간격 옵션</span><span class="sxs-lookup"><span data-stu-id="d1f54-171">Spacing options</span></span>](#spacing-options)
  - <span data-ttu-id="d1f54-172">csharp_space_after_cast</span><span class="sxs-lookup"><span data-stu-id="d1f54-172">csharp_space_after_cast</span></span>
  - <span data-ttu-id="d1f54-173">csharp_space_after_keywords_in_control_flow_statements</span><span class="sxs-lookup"><span data-stu-id="d1f54-173">csharp_space_after_keywords_in_control_flow_statements</span></span>
  - <span data-ttu-id="d1f54-174">csharp_space_between_parentheses</span><span class="sxs-lookup"><span data-stu-id="d1f54-174">csharp_space_between_parentheses</span></span>
  - <span data-ttu-id="d1f54-175">csharp_space_before_colon_in_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="d1f54-175">csharp_space_before_colon_in_inheritance_clause</span></span>
  - <span data-ttu-id="d1f54-176">csharp_space_after_colon_in_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="d1f54-176">csharp_space_after_colon_in_inheritance_clause</span></span>
  - <span data-ttu-id="d1f54-177">csharp_space_around_binary_operators</span><span class="sxs-lookup"><span data-stu-id="d1f54-177">csharp_space_around_binary_operators</span></span>
  - <span data-ttu-id="d1f54-178">csharp_space_between_method_declaration_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="d1f54-178">csharp_space_between_method_declaration_parameter_list_parentheses</span></span>
  - <span data-ttu-id="d1f54-179">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="d1f54-179">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span></span>
  - <span data-ttu-id="d1f54-180">csharp_space_between_method_declaration_name_and_open_parenthesis</span><span class="sxs-lookup"><span data-stu-id="d1f54-180">csharp_space_between_method_declaration_name_and_open_parenthesis</span></span>
  - <span data-ttu-id="d1f54-181">csharp_space_between_method_call_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="d1f54-181">csharp_space_between_method_call_parameter_list_parentheses</span></span>
  - <span data-ttu-id="d1f54-182">csharp_space_between_method_call_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="d1f54-182">csharp_space_between_method_call_empty_parameter_list_parentheses</span></span>
  - <span data-ttu-id="d1f54-183">csharp_space_between_method_call_name_and_opening_parenthesis</span><span class="sxs-lookup"><span data-stu-id="d1f54-183">csharp_space_between_method_call_name_and_opening_parenthesis</span></span>
  - <span data-ttu-id="d1f54-184">csharp_space_after_comma</span><span class="sxs-lookup"><span data-stu-id="d1f54-184">csharp_space_after_comma</span></span>
  - <span data-ttu-id="d1f54-185">csharp_space_before_comma</span><span class="sxs-lookup"><span data-stu-id="d1f54-185">csharp_space_before_comma</span></span>
  - <span data-ttu-id="d1f54-186">csharp_space_after_dot</span><span class="sxs-lookup"><span data-stu-id="d1f54-186">csharp_space_after_dot</span></span>
  - <span data-ttu-id="d1f54-187">csharp_space_before_dot</span><span class="sxs-lookup"><span data-stu-id="d1f54-187">csharp_space_before_dot</span></span>
  - <span data-ttu-id="d1f54-188">csharp_space_after_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="d1f54-188">csharp_space_after_semicolon_in_for_statement</span></span>
  - <span data-ttu-id="d1f54-189">csharp_space_before_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="d1f54-189">csharp_space_before_semicolon_in_for_statement</span></span>
  - <span data-ttu-id="d1f54-190">csharp_space_around_declaration_statements</span><span class="sxs-lookup"><span data-stu-id="d1f54-190">csharp_space_around_declaration_statements</span></span>
  - <span data-ttu-id="d1f54-191">csharp_space_before_open_square_brackets</span><span class="sxs-lookup"><span data-stu-id="d1f54-191">csharp_space_before_open_square_brackets</span></span>
  - <span data-ttu-id="d1f54-192">csharp_space_between_empty_square_brackets</span><span class="sxs-lookup"><span data-stu-id="d1f54-192">csharp_space_between_empty_square_brackets</span></span>
  - <span data-ttu-id="d1f54-193">csharp_space_between_square_brackets</span><span class="sxs-lookup"><span data-stu-id="d1f54-193">csharp_space_between_square_brackets</span></span>
- [<span data-ttu-id="d1f54-194">줄 바꿈 옵션</span><span class="sxs-lookup"><span data-stu-id="d1f54-194">Wrap options</span></span>](#wrap-options)
  - <span data-ttu-id="d1f54-195">csharp_preserve_single_line_statements</span><span class="sxs-lookup"><span data-stu-id="d1f54-195">csharp_preserve_single_line_statements</span></span>
  - <span data-ttu-id="d1f54-196">csharp_preserve_single_line_blocks</span><span class="sxs-lookup"><span data-stu-id="d1f54-196">csharp_preserve_single_line_blocks</span></span>
- [<span data-ttu-id="d1f54-197">지시문 옵션 사용</span><span class="sxs-lookup"><span data-stu-id="d1f54-197">Using directive options</span></span>](#using-directive-options)
  - <span data-ttu-id="d1f54-198">csharp_using_directive_placement</span><span class="sxs-lookup"><span data-stu-id="d1f54-198">csharp_using_directive_placement</span></span>

### <a name="new-line-options"></a><span data-ttu-id="d1f54-199">줄 바꿈 옵션</span><span class="sxs-lookup"><span data-stu-id="d1f54-199">New-line options</span></span>

<span data-ttu-id="d1f54-200">이러한 서식 지정 규칙은 코드의 서식을 지정하기 위해 새 줄을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-200">These formatting rules concern the use of new lines to format code.</span></span>

<span data-ttu-id="d1f54-201">예제 *.editorconfig* 파일:</span><span class="sxs-lookup"><span data-stu-id="d1f54-201">Example *.editorconfig* file:</span></span>

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

#### <a name="csharp_new_line_before_open_brace"></a><span data-ttu-id="d1f54-202">csharp\_new\_line\_before\_open_brace</span><span class="sxs-lookup"><span data-stu-id="d1f54-202">csharp\_new\_line\_before\_open_brace</span></span>

<span data-ttu-id="d1f54-203">이 규칙은 중괄호 `{`가 앞의 코드와 동일한 줄 또는 새 줄에 배치되어야 하는지를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-203">This rule concerns whether an open brace `{` should be placed on the same line as the preceding code, or on a new line.</span></span> <span data-ttu-id="d1f54-204">이 규칙의 경우 **모두**, **없음** 또는 하나 이상의 코드 요소(예: **메서드** 또는 **속성**)를 지정하여 이 규칙을 적용할 시점을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-204">For this rule, you specify **all**, **none**, or one or more code elements such as **methods** or **properties**, to define when this rule should be applied.</span></span> <span data-ttu-id="d1f54-205">여러 개의 코드 요소를 지정하려면 쉼표(,)로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-205">To specify multiple code elements, separate them with a comma (,).</span></span>

|<span data-ttu-id="d1f54-206">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-206">Property</span></span>|<span data-ttu-id="d1f54-207">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-207">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-208">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-208">**Option name**</span></span> | <span data-ttu-id="d1f54-209">csharp_new_line_before_open_brace</span><span class="sxs-lookup"><span data-stu-id="d1f54-209">csharp_new_line_before_open_brace</span></span> |
| <span data-ttu-id="d1f54-210">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-210">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-211">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-211">C#</span></span> |
| <span data-ttu-id="d1f54-212">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-212">**Introduced version**</span></span> | <span data-ttu-id="d1f54-213">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d1f54-213">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d1f54-214">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-214">**Option values**</span></span> | <span data-ttu-id="d1f54-215">`all` - 모든 식에서 중괄호를 새 줄에 배치해야 합니다(“Allman” 스타일).</span><span class="sxs-lookup"><span data-stu-id="d1f54-215">`all` - Require braces to be on a new line for all expressions ("Allman" style).</span></span><br /><br /><span data-ttu-id="d1f54-216">`none` - 모든 식에서 중괄호를 동일한 줄에 배치해야 합니다(“K&R”).</span><span class="sxs-lookup"><span data-stu-id="d1f54-216">`none` - Require braces to be on the same line for all expressions ("K&R").</span></span><br /><br /><span data-ttu-id="d1f54-217">`accessors`, `anonymous_methods`, `anonymous_types`, `control_blocks`, `events`, `indexers`, `lambdas`, `local_functions`, `methods`, `object_collection_array_initializers`, `properties`, `types` - 지정된 코드 요소에서 중괄호를 새 줄에 배치해야 합니다(“Allman” 스타일).</span><span class="sxs-lookup"><span data-stu-id="d1f54-217">`accessors`, `anonymous_methods`, `anonymous_types`, `control_blocks`, `events`, `indexers`, `lambdas`, `local_functions`, `methods`, `object_collection_array_initializers`, `properties`, `types` - Require braces to be on a new line for the specified code element ("Allman" style).</span></span> |

<span data-ttu-id="d1f54-218">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-218">Code examples:</span></span>

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

#### <a name="csharp_new_line_before_else"></a><span data-ttu-id="d1f54-219">csharp\_new\_line\_before_else</span><span class="sxs-lookup"><span data-stu-id="d1f54-219">csharp\_new\_line\_before_else</span></span>

|<span data-ttu-id="d1f54-220">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-220">Property</span></span>|<span data-ttu-id="d1f54-221">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-221">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-222">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-222">**Option name**</span></span> | <span data-ttu-id="d1f54-223">csharp_new_line_before_else</span><span class="sxs-lookup"><span data-stu-id="d1f54-223">csharp_new_line_before_else</span></span> |
| <span data-ttu-id="d1f54-224">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-224">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-225">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-225">C#</span></span> |
| <span data-ttu-id="d1f54-226">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-226">**Introduced version**</span></span> | <span data-ttu-id="d1f54-227">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d1f54-227">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d1f54-228">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-228">**Option values**</span></span> | <span data-ttu-id="d1f54-229">`true` - `else` 문을 새 줄에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-229">`true` - Place `else` statements on a new line.</span></span><br /><br /><span data-ttu-id="d1f54-230">`false` - `else` 문을 동일한 줄에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-230">`false` - Place `else` statements on the same line.</span></span> |

<span data-ttu-id="d1f54-231">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-231">Code examples:</span></span>

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

#### <a name="csharp_new_line_before_catch"></a><span data-ttu-id="d1f54-232">csharp\_new\_line\_before_catch</span><span class="sxs-lookup"><span data-stu-id="d1f54-232">csharp\_new\_line\_before_catch</span></span>

|<span data-ttu-id="d1f54-233">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-233">Property</span></span>|<span data-ttu-id="d1f54-234">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-234">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-235">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-235">**Option name**</span></span> | <span data-ttu-id="d1f54-236">csharp_new_line_before_catch</span><span class="sxs-lookup"><span data-stu-id="d1f54-236">csharp_new_line_before_catch</span></span> |
| <span data-ttu-id="d1f54-237">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-237">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-238">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-238">C#</span></span> |
| <span data-ttu-id="d1f54-239">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-239">**Introduced version**</span></span> | <span data-ttu-id="d1f54-240">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d1f54-240">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d1f54-241">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-241">**Option values**</span></span> | <span data-ttu-id="d1f54-242">`true` - `catch` 문을 새 줄에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-242">`true` - Place `catch` statements on a new line.</span></span><br /><br /><span data-ttu-id="d1f54-243">`false` - `catch` 문을 동일한 줄에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-243">`false` - Place `catch` statements on the same line.</span></span> |

<span data-ttu-id="d1f54-244">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-244">Code examples:</span></span>

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

#### <a name="csharp_new_line_before_finally"></a><span data-ttu-id="d1f54-245">csharp\_new\_line\_before_finally</span><span class="sxs-lookup"><span data-stu-id="d1f54-245">csharp\_new\_line\_before_finally</span></span>

|<span data-ttu-id="d1f54-246">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-246">Property</span></span>|<span data-ttu-id="d1f54-247">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-247">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-248">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-248">**Option name**</span></span> | <span data-ttu-id="d1f54-249">csharp_new_line_before_finally</span><span class="sxs-lookup"><span data-stu-id="d1f54-249">csharp_new_line_before_finally</span></span> |
| <span data-ttu-id="d1f54-250">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-250">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-251">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-251">C#</span></span> |
| <span data-ttu-id="d1f54-252">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-252">**Introduced version**</span></span> | <span data-ttu-id="d1f54-253">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d1f54-253">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d1f54-254">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-254">**Option values**</span></span> | <span data-ttu-id="d1f54-255">`true` - `finally` 문을 닫는 괄호 뒤의 새 줄에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-255">`true` - Require `finally` statements to be on a new line after the closing brace.</span></span><br /><br /><span data-ttu-id="d1f54-256">`false` - `finally` 문을 닫는 괄호와 동일한 줄에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-256">`false` - Require `finally` statements to be on the same line as the closing brace.</span></span> |

<span data-ttu-id="d1f54-257">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-257">Code examples:</span></span>

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

#### <a name="csharp_new_line_before_members_in_object_initializers"></a><span data-ttu-id="d1f54-258">csharp\_new\_line\_before\_members\_in\_object_initializers</span><span class="sxs-lookup"><span data-stu-id="d1f54-258">csharp\_new\_line\_before\_members\_in\_object_initializers</span></span>

|<span data-ttu-id="d1f54-259">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-259">Property</span></span>|<span data-ttu-id="d1f54-260">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-260">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-261">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-261">**Option name**</span></span> | <span data-ttu-id="d1f54-262">csharp_new_line_before_members_in_object_initializers</span><span class="sxs-lookup"><span data-stu-id="d1f54-262">csharp_new_line_before_members_in_object_initializers</span></span> |
| <span data-ttu-id="d1f54-263">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-263">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-264">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-264">C#</span></span> |
| <span data-ttu-id="d1f54-265">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-265">**Introduced version**</span></span> | <span data-ttu-id="d1f54-266">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d1f54-266">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d1f54-267">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-267">**Option values**</span></span> | <span data-ttu-id="d1f54-268">`true` - 개체 이니셜라이저의 멤버를 새 줄에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-268">`true` - Require members of object initializers to be on separate lines</span></span><br /><br /><span data-ttu-id="d1f54-269">`false` - 개체 이니셜라이저의 멤버를 동일한 줄에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-269">`false` - Require members of object initializers to be on the same line</span></span> |

<span data-ttu-id="d1f54-270">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-270">Code examples:</span></span>

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

#### <a name="csharp_new_line_before_members_in_anonymous_types"></a><span data-ttu-id="d1f54-271">csharp\_new\_line\_before\_members\_in\_anonymous_types</span><span class="sxs-lookup"><span data-stu-id="d1f54-271">csharp\_new\_line\_before\_members\_in\_anonymous_types</span></span>

|<span data-ttu-id="d1f54-272">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-272">Property</span></span>|<span data-ttu-id="d1f54-273">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-273">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-274">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-274">**Option name**</span></span> | <span data-ttu-id="d1f54-275">csharp_new_line_before_members_in_anonymous_types</span><span class="sxs-lookup"><span data-stu-id="d1f54-275">csharp_new_line_before_members_in_anonymous_types</span></span> |
| <span data-ttu-id="d1f54-276">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-276">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-277">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-277">C#</span></span> |
| <span data-ttu-id="d1f54-278">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-278">**Introduced version**</span></span> | <span data-ttu-id="d1f54-279">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d1f54-279">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d1f54-280">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-280">**Option values**</span></span> | <span data-ttu-id="d1f54-281">`true` - 무명 형식의 멤버를 새 줄에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-281">`true` - Require members of anonymous types to be on separate lines</span></span><br /><br /><span data-ttu-id="d1f54-282">`false` - 무명 형식의 멤버를 동일한 줄에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-282">`false` - Require members of anonymous types to be on the same line</span></span> |

<span data-ttu-id="d1f54-283">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-283">Code examples:</span></span>

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

#### <a name="csharp_new_line_between_query_expression_clauses"></a><span data-ttu-id="d1f54-284">csharp_new_line_between_query_expression_clauses</span><span class="sxs-lookup"><span data-stu-id="d1f54-284">csharp_new_line_between_query_expression_clauses</span></span>

|<span data-ttu-id="d1f54-285">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-285">Property</span></span>|<span data-ttu-id="d1f54-286">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-286">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-287">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-287">**Option name**</span></span> | <span data-ttu-id="d1f54-288">csharp_new_line_between_query_expression_clauses</span><span class="sxs-lookup"><span data-stu-id="d1f54-288">csharp_new_line_between_query_expression_clauses</span></span> |
| <span data-ttu-id="d1f54-289">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-289">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-290">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-290">C#</span></span> |
| <span data-ttu-id="d1f54-291">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-291">**Introduced version**</span></span> | <span data-ttu-id="d1f54-292">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d1f54-292">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d1f54-293">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-293">**Option values**</span></span> | <span data-ttu-id="d1f54-294">`true` - 쿼리 식 절의 요소를 새 줄에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-294">`true` - Require elements of query expression clauses to be on separate lines</span></span><br /><br /><span data-ttu-id="d1f54-295">`false` - 쿼리 식 절의 요소를 동일한 줄에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-295">`false` - Require elements of query expression clauses to be on the same line</span></span> |

<span data-ttu-id="d1f54-296">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-296">Code examples:</span></span>

```csharp
// csharp_new_line_between_query_expression_clauses = true
var q = from a in e
        from b in e
        select a * b;

// csharp_new_line_between_query_expression_clauses = false
var q = from a in e from b in e
        select a * b;
```

### <a name="indentation-options"></a><span data-ttu-id="d1f54-297">들여쓰기 옵션</span><span class="sxs-lookup"><span data-stu-id="d1f54-297">Indentation options</span></span>

<span data-ttu-id="d1f54-298">이러한 서식 지정 규칙은 코드의 서식을 지정하기 위해 들여쓰기를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-298">These formatting rules concern the use of indentation to format code.</span></span>

<span data-ttu-id="d1f54-299">예제 *.editorconfig* 파일:</span><span class="sxs-lookup"><span data-stu-id="d1f54-299">Example *.editorconfig* file:</span></span>

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

#### <a name="csharp_indent_case_contents"></a><span data-ttu-id="d1f54-300">csharp\_indent\_case_contents</span><span class="sxs-lookup"><span data-stu-id="d1f54-300">csharp\_indent\_case_contents</span></span>

|<span data-ttu-id="d1f54-301">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-301">Property</span></span>|<span data-ttu-id="d1f54-302">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-302">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-303">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-303">**Option name**</span></span> | <span data-ttu-id="d1f54-304">csharp_indent_case_contents</span><span class="sxs-lookup"><span data-stu-id="d1f54-304">csharp_indent_case_contents</span></span> |
| <span data-ttu-id="d1f54-305">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-305">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-306">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-306">C#</span></span> |
| <span data-ttu-id="d1f54-307">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-307">**Introduced version**</span></span> | <span data-ttu-id="d1f54-308">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d1f54-308">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d1f54-309">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-309">**Option values**</span></span> | <span data-ttu-id="d1f54-310">`true` - `switch` case 콘텐츠를 들여씁니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-310">`true` - Indent `switch` case contents</span></span><br /><br /><span data-ttu-id="d1f54-311">`false` - `switch` case 콘텐츠를 들여 쓰지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-311">`false` - Do not indent `switch` case contents</span></span> |

- <span data-ttu-id="d1f54-312">이 규칙을 **true** 로 설정한 경우 i입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-312">When this rule is set to **true**, i.</span></span>
- <span data-ttu-id="d1f54-313">이 규칙을 **false** 로 설정한 경우 d입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-313">When this rule is set to **false**, d.</span></span>

<span data-ttu-id="d1f54-314">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-314">Code examples:</span></span>

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

#### <a name="csharp_indent_switch_labels"></a><span data-ttu-id="d1f54-315">csharp\_indent\_switch_labels</span><span class="sxs-lookup"><span data-stu-id="d1f54-315">csharp\_indent\_switch_labels</span></span>

|<span data-ttu-id="d1f54-316">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-316">Property</span></span>|<span data-ttu-id="d1f54-317">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-317">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-318">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-318">**Option name**</span></span> | <span data-ttu-id="d1f54-319">csharp_indent_switch_labels</span><span class="sxs-lookup"><span data-stu-id="d1f54-319">csharp_indent_switch_labels</span></span> |
| <span data-ttu-id="d1f54-320">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-320">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-321">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-321">C#</span></span> |
| <span data-ttu-id="d1f54-322">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-322">**Introduced version**</span></span> | <span data-ttu-id="d1f54-323">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d1f54-323">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d1f54-324">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-324">**Option values**</span></span> | <span data-ttu-id="d1f54-325">`true` - `switch` 레이블을 들여씁니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-325">`true` - Indent `switch` labels</span></span><br /><br /><span data-ttu-id="d1f54-326">`false` - `switch` 레이블을 들여 쓰지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-326">`false` - Do not indent `switch` labels</span></span> |

<span data-ttu-id="d1f54-327">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-327">Code examples:</span></span>

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

#### <a name="csharp_indent_labels"></a><span data-ttu-id="d1f54-328">csharp\_indent_labels</span><span class="sxs-lookup"><span data-stu-id="d1f54-328">csharp\_indent_labels</span></span>

|<span data-ttu-id="d1f54-329">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-329">Property</span></span>|<span data-ttu-id="d1f54-330">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-330">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-331">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-331">**Option name**</span></span> | <span data-ttu-id="d1f54-332">csharp_indent_labels</span><span class="sxs-lookup"><span data-stu-id="d1f54-332">csharp_indent_labels</span></span> |
| <span data-ttu-id="d1f54-333">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-333">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-334">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-334">C#</span></span> |
| <span data-ttu-id="d1f54-335">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-335">**Introduced version**</span></span> | <span data-ttu-id="d1f54-336">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d1f54-336">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d1f54-337">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-337">**Option values**</span></span> | <span data-ttu-id="d1f54-338">`flush_left` - 레이블이 가장 왼쪽 열에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-338">`flush_left` - Labels are placed at the leftmost column</span></span><br /><br /><span data-ttu-id="d1f54-339">`one_less_than_current` - 레이블이 현재 컨텍스트보다 한 수준 더 들여쓰기에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-339">`one_less_than_current` - Labels are placed at one less indent to the current context</span></span><br /><br /><span data-ttu-id="d1f54-340">`no_change` - 레이블이 현재 컨텍스트와 동일한 들여쓰기에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-340">`no_change` - Labels are placed at the same indent as the current context</span></span> |

<span data-ttu-id="d1f54-341">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-341">Code examples:</span></span>

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

#### <a name="csharp_indent_block_contents"></a><span data-ttu-id="d1f54-342">csharp_indent_block_contents</span><span class="sxs-lookup"><span data-stu-id="d1f54-342">csharp_indent_block_contents</span></span>

|<span data-ttu-id="d1f54-343">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-343">Property</span></span>|<span data-ttu-id="d1f54-344">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-344">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-345">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-345">**Option name**</span></span> | <span data-ttu-id="d1f54-346">csharp_indent_block_contents</span><span class="sxs-lookup"><span data-stu-id="d1f54-346">csharp_indent_block_contents</span></span> |
| <span data-ttu-id="d1f54-347">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-347">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-348">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-348">C#</span></span> |
| <span data-ttu-id="d1f54-349">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-349">**Option values**</span></span> | `true` - <br /><br />`false` -  |

<span data-ttu-id="d1f54-350">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-350">Code examples:</span></span>

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

#### <a name="csharp_indent_braces"></a><span data-ttu-id="d1f54-351">csharp_indent_braces</span><span class="sxs-lookup"><span data-stu-id="d1f54-351">csharp_indent_braces</span></span>

|<span data-ttu-id="d1f54-352">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-352">Property</span></span>|<span data-ttu-id="d1f54-353">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-353">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-354">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-354">**Option name**</span></span> | <span data-ttu-id="d1f54-355">csharp_indent_braces</span><span class="sxs-lookup"><span data-stu-id="d1f54-355">csharp_indent_braces</span></span> |
| <span data-ttu-id="d1f54-356">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-356">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-357">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-357">C#</span></span> |
| <span data-ttu-id="d1f54-358">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-358">**Option values**</span></span> | `true` - <br /><br />`false` -  |

<span data-ttu-id="d1f54-359">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-359">Code examples:</span></span>

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

#### <a name="csharp_indent_case_contents_when_block"></a><span data-ttu-id="d1f54-360">csharp_indent_case_contents_when_block</span><span class="sxs-lookup"><span data-stu-id="d1f54-360">csharp_indent_case_contents_when_block</span></span>

|<span data-ttu-id="d1f54-361">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-361">Property</span></span>|<span data-ttu-id="d1f54-362">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-362">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-363">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-363">**Option name**</span></span> | <span data-ttu-id="d1f54-364">csharp_indent_case_contents_when_block</span><span class="sxs-lookup"><span data-stu-id="d1f54-364">csharp_indent_case_contents_when_block</span></span> |
| <span data-ttu-id="d1f54-365">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-365">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-366">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-366">C#</span></span> |
| <span data-ttu-id="d1f54-367">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-367">**Option values**</span></span> | `true` - <br /><br />`false` -  |

<span data-ttu-id="d1f54-368">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-368">Code examples:</span></span>

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

### <a name="spacing-options"></a><span data-ttu-id="d1f54-369">간격 옵션</span><span class="sxs-lookup"><span data-stu-id="d1f54-369">Spacing options</span></span>

<span data-ttu-id="d1f54-370">이러한 서식 지정 규칙은 코드의 서식을 지정하기 위해 공백 문자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-370">These formatting rules concern the use of space characters to format code.</span></span>

<span data-ttu-id="d1f54-371">예제 *.editorconfig* 파일:</span><span class="sxs-lookup"><span data-stu-id="d1f54-371">Example *.editorconfig* file:</span></span>

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

#### <a name="csharp_space_after_cast"></a><span data-ttu-id="d1f54-372">csharp\_space\_after_cast</span><span class="sxs-lookup"><span data-stu-id="d1f54-372">csharp\_space\_after_cast</span></span>

|<span data-ttu-id="d1f54-373">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-373">Property</span></span>|<span data-ttu-id="d1f54-374">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-374">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-375">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-375">**Option name**</span></span> | <span data-ttu-id="d1f54-376">csharp_space_after_cast</span><span class="sxs-lookup"><span data-stu-id="d1f54-376">csharp_space_after_cast</span></span> |
| <span data-ttu-id="d1f54-377">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-377">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-378">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-378">C#</span></span> |
| <span data-ttu-id="d1f54-379">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-379">**Introduced version**</span></span> | <span data-ttu-id="d1f54-380">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d1f54-380">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d1f54-381">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-381">**Option values**</span></span> | <span data-ttu-id="d1f54-382">`true` - 캐스트와 값 사이에 공백 문자를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-382">`true` - Place a space character between a cast and the value</span></span><br /><br /><span data-ttu-id="d1f54-383">`false` - 캐스트와 값 사이에서 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-383">`false` - Remove space between the cast and the value</span></span> |

<span data-ttu-id="d1f54-384">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-384">Code examples:</span></span>

```csharp
// csharp_space_after_cast = true
int y = (int) x;

// csharp_space_after_cast = false
int y = (int)x;
```

#### <a name="csharp_space_after_keywords_in_control_flow_statements"></a><span data-ttu-id="d1f54-385">csharp_space_after_keywords_in_control_flow_statements</span><span class="sxs-lookup"><span data-stu-id="d1f54-385">csharp_space_after_keywords_in_control_flow_statements</span></span>

|<span data-ttu-id="d1f54-386">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-386">Property</span></span>|<span data-ttu-id="d1f54-387">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-387">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-388">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-388">**Option name**</span></span> | <span data-ttu-id="d1f54-389">csharp_space_after_keywords_in_control_flow_statements</span><span class="sxs-lookup"><span data-stu-id="d1f54-389">csharp_space_after_keywords_in_control_flow_statements</span></span> |
| <span data-ttu-id="d1f54-390">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-390">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-391">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-391">C#</span></span> |
| <span data-ttu-id="d1f54-392">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-392">**Introduced version**</span></span> | <span data-ttu-id="d1f54-393">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d1f54-393">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d1f54-394">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-394">**Option values**</span></span> | <span data-ttu-id="d1f54-395">`true` - `for` 루프와 같은 제어 흐름 문의 키워드 뒤에 공백 문자를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-395">`true` - Place a space character after a keyword in a control flow statement such as a `for` loop</span></span><br /><br /><span data-ttu-id="d1f54-396">`false` - `for` 루프와 같은 제어 흐름 문의 키워드 뒤에서 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-396">`false` - Remove space after a keyword in a control flow statement such as a `for` loop</span></span> |

<span data-ttu-id="d1f54-397">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-397">Code examples:</span></span>

```csharp
// csharp_space_after_keywords_in_control_flow_statements = true
for (int i;i<x;i++) { ... }

// csharp_space_after_keywords_in_control_flow_statements = false
for(int i;i<x;i++) { ... }
```

#### <a name="csharp_space_between_parentheses"></a><span data-ttu-id="d1f54-398">csharp_space_between_parentheses</span><span class="sxs-lookup"><span data-stu-id="d1f54-398">csharp_space_between_parentheses</span></span>

|<span data-ttu-id="d1f54-399">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-399">Property</span></span>|<span data-ttu-id="d1f54-400">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-400">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-401">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-401">**Option name**</span></span> | <span data-ttu-id="d1f54-402">csharp_space_between_parentheses</span><span class="sxs-lookup"><span data-stu-id="d1f54-402">csharp_space_between_parentheses</span></span> |
| <span data-ttu-id="d1f54-403">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-403">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-404">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-404">C#</span></span> |
| <span data-ttu-id="d1f54-405">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-405">**Introduced version**</span></span> | <span data-ttu-id="d1f54-406">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d1f54-406">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d1f54-407">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-407">**Option values**</span></span> | <span data-ttu-id="d1f54-408">`control_flow_statements` - 제어 흐름 문의 괄호 사이에 공백을 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-408">`control_flow_statements` - Place space between parentheses of control flow statements</span></span><br /><br /><span data-ttu-id="d1f54-409">`expressions` - 식의 괄호 사이에 공백을 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-409">`expressions` - Place space between parentheses of expressions</span></span><br /><br /><span data-ttu-id="d1f54-410">`type_casts` - 형식 캐스트의 괄호 사이에 공백을 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-410">`type_casts` - Place space between parentheses in type casts</span></span> |

<span data-ttu-id="d1f54-411">이 규칙을 생략하거나 `control_flow_statements`, `expressions` 또는 `type_casts` 이외의 값을 사용하면 설정이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-411">If you omit this rule or use a value other than `control_flow_statements`, `expressions`, or `type_casts`, the setting is not applied.</span></span>

<span data-ttu-id="d1f54-412">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-412">Code examples:</span></span>

```csharp
// csharp_space_between_parentheses = control_flow_statements
for ( int i = 0; i < 10; i++ ) { }

// csharp_space_between_parentheses = expressions
var z = ( x * y ) - ( ( y - x ) * 3 );

// csharp_space_between_parentheses = type_casts
int y = ( int )x;
```

#### <a name="csharp_space_before_colon_in_inheritance_clause"></a><span data-ttu-id="d1f54-413">csharp\_space\_before\_colon\_in\_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="d1f54-413">csharp\_space\_before\_colon\_in\_inheritance_clause</span></span>

|<span data-ttu-id="d1f54-414">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-414">Property</span></span>|<span data-ttu-id="d1f54-415">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-415">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-416">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-416">**Option name**</span></span> | <span data-ttu-id="d1f54-417">csharp_space_before_colon_in_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="d1f54-417">csharp_space_before_colon_in_inheritance_clause</span></span> |
| <span data-ttu-id="d1f54-418">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-418">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-419">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-419">C#</span></span> |
| <span data-ttu-id="d1f54-420">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-420">**Introduced version**</span></span> | <span data-ttu-id="d1f54-421">Visual Studio 2017 버전 15.7</span><span class="sxs-lookup"><span data-stu-id="d1f54-421">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="d1f54-422">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-422">**Option values**</span></span> | <span data-ttu-id="d1f54-423">`true` - 형식 선언에서 베이스 또는 인터페이스의 콜론 앞에 공백 문자를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-423">`true` - Place a space character before the colon for bases or interfaces in a type declaration</span></span><br /><br /><span data-ttu-id="d1f54-424">`false` - 형식 선언에서 베이스 또는 인터페이스의 콜론 앞에서 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-424">`false` - Remove space before the colon for bases or interfaces in a type declaration</span></span> |

<span data-ttu-id="d1f54-425">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-425">Code examples:</span></span>

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

#### <a name="csharp_space_after_colon_in_inheritance_clause"></a><span data-ttu-id="d1f54-426">csharp\_space\_after\_colon\_in\_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="d1f54-426">csharp\_space\_after\_colon\_in\_inheritance_clause</span></span>

|<span data-ttu-id="d1f54-427">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-427">Property</span></span>|<span data-ttu-id="d1f54-428">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-428">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-429">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-429">**Option name**</span></span> | <span data-ttu-id="d1f54-430">csharp_space_after_colon_in_inheritance_clause</span><span class="sxs-lookup"><span data-stu-id="d1f54-430">csharp_space_after_colon_in_inheritance_clause</span></span> |
| <span data-ttu-id="d1f54-431">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-431">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-432">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-432">C#</span></span> |
| <span data-ttu-id="d1f54-433">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-433">**Introduced version**</span></span> | <span data-ttu-id="d1f54-434">Visual Studio 2017 버전 15.7</span><span class="sxs-lookup"><span data-stu-id="d1f54-434">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="d1f54-435">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-435">**Option values**</span></span> | <span data-ttu-id="d1f54-436">`true` - 형식 선언에서 베이스 또는 인터페이스의 콜론 뒤에 공백 문자를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-436">`true` - Place a space character after the colon for bases or interfaces in a type declaration</span></span><br /><br /><span data-ttu-id="d1f54-437">`false` - 형식 선언에서 베이스 또는 인터페이스의 콜론 뒤에서 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-437">`false` - Remove space after the colon for bases or interfaces in a type declaration</span></span> |

<span data-ttu-id="d1f54-438">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-438">Code examples:</span></span>

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

#### <a name="csharp_space_around_binary_operators"></a><span data-ttu-id="d1f54-439">csharp\_space\_around\_binary_operators</span><span class="sxs-lookup"><span data-stu-id="d1f54-439">csharp\_space\_around\_binary_operators</span></span>

|<span data-ttu-id="d1f54-440">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-440">Property</span></span>|<span data-ttu-id="d1f54-441">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-441">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-442">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-442">**Option name**</span></span> | <span data-ttu-id="d1f54-443">csharp_space_around_binary_operators</span><span class="sxs-lookup"><span data-stu-id="d1f54-443">csharp_space_around_binary_operators</span></span> |
| <span data-ttu-id="d1f54-444">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-444">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-445">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-445">C#</span></span> |
| <span data-ttu-id="d1f54-446">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-446">**Introduced version**</span></span> | <span data-ttu-id="d1f54-447">Visual Studio 2017 버전 15.7</span><span class="sxs-lookup"><span data-stu-id="d1f54-447">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="d1f54-448">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-448">**Option values**</span></span> | <span data-ttu-id="d1f54-449">`before_and_after` - 이항 연산자 앞뒤에 공백을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-449">`before_and_after` - Insert space before and after the binary operator</span></span><br /><br /><span data-ttu-id="d1f54-450">`none` - 이항 연산자 앞뒤의 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-450">`none` - Remove spaces before and after the binary operator</span></span><br /><br /><span data-ttu-id="d1f54-451">`ignore` - 이항 연산자 주위의 공백을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-451">`ignore` - Ignore spaces around binary operators</span></span> |

<span data-ttu-id="d1f54-452">이 규칙을 생략하거나 `before_and_after`, `none` 또는 `ignore` 이외의 값을 사용하는 경우 설정이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-452">If you omit this rule, or use a value other than `before_and_after`, `none`, or `ignore`, the setting is not applied.</span></span>

<span data-ttu-id="d1f54-453">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-453">Code examples:</span></span>

```csharp
// csharp_space_around_binary_operators = before_and_after
return x * (x - y);

// csharp_space_around_binary_operators = none
return x*(x-y);

// csharp_space_around_binary_operators = ignore
return x  *  (x-y);
```

#### <a name="csharp_space_between_method_declaration_parameter_list_parentheses"></a><span data-ttu-id="d1f54-454">csharp_space_between_method_declaration_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="d1f54-454">csharp_space_between_method_declaration_parameter_list_parentheses</span></span>

|<span data-ttu-id="d1f54-455">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-455">Property</span></span>|<span data-ttu-id="d1f54-456">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-456">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-457">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-457">**Option name**</span></span> | <span data-ttu-id="d1f54-458">csharp_space_between_method_declaration_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="d1f54-458">csharp_space_between_method_declaration_parameter_list_parentheses</span></span> |
| <span data-ttu-id="d1f54-459">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-459">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-460">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-460">C#</span></span> |
| <span data-ttu-id="d1f54-461">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-461">**Introduced version**</span></span> | <span data-ttu-id="d1f54-462">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d1f54-462">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d1f54-463">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-463">**Option values**</span></span> | <span data-ttu-id="d1f54-464">`true` - 여는 괄호 뒤 및 메서드 선언 매개 변수 목록의 닫는 괄호 앞에 공백 문자를 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-464">`true` - Place a space character after the opening parenthesis and before the closing parenthesis of a method declaration parameter list</span></span><br /><br /><span data-ttu-id="d1f54-465">`false` - 여는 괄호 뒤 및 메서드 선언 매개 변수 목록의 닫는 괄호 앞에서 공백 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-465">`false` - Remove space characters after the opening parenthesis and before the closing parenthesis of a method declaration parameter list</span></span> |

<span data-ttu-id="d1f54-466">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-466">Code examples:</span></span>

```csharp
// csharp_space_between_method_declaration_parameter_list_parentheses = true
void Bark( int x ) { ... }

// csharp_space_between_method_declaration_parameter_list_parentheses = false
void Bark(int x) { ... }
```

#### <a name="csharp_space_between_method_declaration_empty_parameter_list_parentheses"></a><span data-ttu-id="d1f54-467">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="d1f54-467">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span></span>

|<span data-ttu-id="d1f54-468">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-468">Property</span></span>|<span data-ttu-id="d1f54-469">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-469">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-470">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-470">**Option name**</span></span> | <span data-ttu-id="d1f54-471">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="d1f54-471">csharp_space_between_method_declaration_empty_parameter_list_parentheses</span></span> |
| <span data-ttu-id="d1f54-472">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-472">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-473">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-473">C#</span></span> |
| <span data-ttu-id="d1f54-474">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-474">**Introduced version**</span></span> | <span data-ttu-id="d1f54-475">Visual Studio 2017 버전 15.7</span><span class="sxs-lookup"><span data-stu-id="d1f54-475">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="d1f54-476">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-476">**Option values**</span></span> | <span data-ttu-id="d1f54-477">`true` - 메서드 선언에서 빈 매개 변수 목록 괄호 안에 공백을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-477">`true` - Insert space within empty parameter list parentheses for a method declaration</span></span><br /><br /><span data-ttu-id="d1f54-478">`false` - 메서드 선언에서 빈 매개 변수 목록 괄호 안의 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-478">`false` - Remove space within empty parameter list parentheses for a method declaration</span></span> |

<span data-ttu-id="d1f54-479">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-479">Code examples:</span></span>

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

#### <a name="csharp_space_between_method_declaration_name_and_open_parenthesis"></a><span data-ttu-id="d1f54-480">csharp_space_between_method_declaration_name_and_open_parenthesis</span><span class="sxs-lookup"><span data-stu-id="d1f54-480">csharp_space_between_method_declaration_name_and_open_parenthesis</span></span>

|<span data-ttu-id="d1f54-481">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-481">Property</span></span>|<span data-ttu-id="d1f54-482">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-482">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-483">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-483">**Option name**</span></span> | <span data-ttu-id="d1f54-484">csharp_space_between_method_declaration_name_and_open_parenthesis</span><span class="sxs-lookup"><span data-stu-id="d1f54-484">csharp_space_between_method_declaration_name_and_open_parenthesis</span></span> |
| <span data-ttu-id="d1f54-485">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-485">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-486">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-486">C#</span></span> |
| <span data-ttu-id="d1f54-487">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-487">**Option values**</span></span> | <span data-ttu-id="d1f54-488">`true` -메서드 선언에서 메서드 이름과 여는 괄호 사이에 공백 문자를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-488">`true` - Place a space character between the method name and opening parenthesis in the method declaration</span></span><br /><br /><span data-ttu-id="d1f54-489">`false` -메서드 선언에서 메서드 이름과 여는 괄호 사이에서 공백 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-489">`false` - Remove space characters between the method name and opening parenthesis in the method declaration</span></span> |

<span data-ttu-id="d1f54-490">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-490">Code examples:</span></span>

```csharp
// csharp_space_between_method_declaration_name_and_open_parenthesis = true
void M () { }

// csharp_space_between_method_declaration_name_and_open_parenthesis = false
void M() { }
```

#### <a name="csharp_space_between_method_call_parameter_list_parentheses"></a><span data-ttu-id="d1f54-491">csharp_space_between_method_call_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="d1f54-491">csharp_space_between_method_call_parameter_list_parentheses</span></span>

|<span data-ttu-id="d1f54-492">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-492">Property</span></span>|<span data-ttu-id="d1f54-493">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-493">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-494">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-494">**Option name**</span></span> | <span data-ttu-id="d1f54-495">csharp_space_between_method_call_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="d1f54-495">csharp_space_between_method_call_parameter_list_parentheses</span></span> |
| <span data-ttu-id="d1f54-496">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-496">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-497">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-497">C#</span></span> |
| <span data-ttu-id="d1f54-498">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-498">**Introduced version**</span></span> | <span data-ttu-id="d1f54-499">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d1f54-499">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d1f54-500">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-500">**Option values**</span></span> | <span data-ttu-id="d1f54-501">`true` - 여는 괄호 뒤 및 메서드 호출의 닫는 괄호 앞에 공백 문자를 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-501">`true` - Place a space character after the opening parenthesis and before the closing parenthesis of a method call</span></span><br /><br /><span data-ttu-id="d1f54-502">`false` - 여는 괄호 뒤 및 메서드 호출의 닫는 괄호 앞에서 공백 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-502">`false` - Remove space characters after the opening parenthesis and before the closing parenthesis of a method call</span></span> |

<span data-ttu-id="d1f54-503">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-503">Code examples:</span></span>

```csharp
// csharp_space_between_method_call_parameter_list_parentheses = true
MyMethod( argument );

// csharp_space_between_method_call_parameter_list_parentheses = false
MyMethod(argument);
```

#### <a name="csharp_space_between_method_call_empty_parameter_list_parentheses"></a><span data-ttu-id="d1f54-504">csharp_space_between_method_call_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="d1f54-504">csharp_space_between_method_call_empty_parameter_list_parentheses</span></span>

|<span data-ttu-id="d1f54-505">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-505">Property</span></span>|<span data-ttu-id="d1f54-506">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-506">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-507">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-507">**Option name**</span></span> | <span data-ttu-id="d1f54-508">csharp_space_between_method_call_empty_parameter_list_parentheses</span><span class="sxs-lookup"><span data-stu-id="d1f54-508">csharp_space_between_method_call_empty_parameter_list_parentheses</span></span> |
| <span data-ttu-id="d1f54-509">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-509">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-510">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-510">C#</span></span> |
| <span data-ttu-id="d1f54-511">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-511">**Introduced version**</span></span> | <span data-ttu-id="d1f54-512">Visual Studio 2017 버전 15.7</span><span class="sxs-lookup"><span data-stu-id="d1f54-512">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="d1f54-513">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-513">**Option values**</span></span> | <span data-ttu-id="d1f54-514">`true` - 빈 인수 목록 괄호 안에 공백을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-514">`true` - Insert space within empty argument list parentheses</span></span><br /><br /><span data-ttu-id="d1f54-515">`false` - 빈 인수 목록 괄호 안의 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-515">`false` - Remove space within empty argument list parentheses</span></span> |

<span data-ttu-id="d1f54-516">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-516">Code examples:</span></span>

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

#### <a name="csharp_space_between_method_call_name_and_opening_parenthesis"></a><span data-ttu-id="d1f54-517">csharp_space_between_method_call_name_and_opening_parenthesis</span><span class="sxs-lookup"><span data-stu-id="d1f54-517">csharp_space_between_method_call_name_and_opening_parenthesis</span></span>

|<span data-ttu-id="d1f54-518">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-518">Property</span></span>|<span data-ttu-id="d1f54-519">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-519">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-520">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-520">**Option name**</span></span> | <span data-ttu-id="d1f54-521">csharp_space_between_method_call_name_and_opening_parenthesis</span><span class="sxs-lookup"><span data-stu-id="d1f54-521">csharp_space_between_method_call_name_and_opening_parenthesis</span></span> |
| <span data-ttu-id="d1f54-522">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-522">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-523">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-523">C#</span></span> |
| <span data-ttu-id="d1f54-524">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-524">**Introduced version**</span></span> | <span data-ttu-id="d1f54-525">Visual Studio 2017 버전 15.7</span><span class="sxs-lookup"><span data-stu-id="d1f54-525">Visual Studio 2017 version 15.7</span></span> |
| <span data-ttu-id="d1f54-526">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-526">**Option values**</span></span> | <span data-ttu-id="d1f54-527">`true` - 메서드 호출 이름과 여는 괄호 사이에 공백을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-527">`true` - Insert space between method call name and opening parenthesis</span></span><br /><br /><span data-ttu-id="d1f54-528">`false` - 메서드 호출 이름과 여는 괄호 사이의 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-528">`false` - Remove space between method call name and opening parenthesis</span></span> |

<span data-ttu-id="d1f54-529">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-529">Code examples:</span></span>

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

#### <a name="csharp_space_after_comma"></a><span data-ttu-id="d1f54-530">csharp_space_after_comma</span><span class="sxs-lookup"><span data-stu-id="d1f54-530">csharp_space_after_comma</span></span>

|<span data-ttu-id="d1f54-531">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-531">Property</span></span>|<span data-ttu-id="d1f54-532">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-532">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-533">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-533">**Option name**</span></span> | <span data-ttu-id="d1f54-534">csharp_space_after_comma</span><span class="sxs-lookup"><span data-stu-id="d1f54-534">csharp_space_after_comma</span></span> |
| <span data-ttu-id="d1f54-535">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-535">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-536">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-536">C#</span></span> |
| <span data-ttu-id="d1f54-537">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-537">**Option values**</span></span> | <span data-ttu-id="d1f54-538">`true` - 쉼표 뒤에 공백을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-538">`true` - Insert space after a comma</span></span><br /><br /><span data-ttu-id="d1f54-539">`false` - 쉼표 뒤의 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-539">`false` - Remove space after a comma</span></span> |

<span data-ttu-id="d1f54-540">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-540">Code examples:</span></span>

```csharp
// csharp_space_after_comma = true
int[] x = new int[] { 1, 2, 3, 4, 5 };

// csharp_space_after_comma = false
int[] x = new int[] { 1,2,3,4,5 }
```

#### <a name="csharp_space_before_comma"></a><span data-ttu-id="d1f54-541">csharp_space_before_comma</span><span class="sxs-lookup"><span data-stu-id="d1f54-541">csharp_space_before_comma</span></span>

|<span data-ttu-id="d1f54-542">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-542">Property</span></span>|<span data-ttu-id="d1f54-543">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-543">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-544">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-544">**Option name**</span></span> | <span data-ttu-id="d1f54-545">csharp_space_before_comma</span><span class="sxs-lookup"><span data-stu-id="d1f54-545">csharp_space_before_comma</span></span> |
| <span data-ttu-id="d1f54-546">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-546">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-547">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-547">C#</span></span> |
| <span data-ttu-id="d1f54-548">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-548">**Option values**</span></span> | <span data-ttu-id="d1f54-549">`true` - 쉼표 앞에 공백을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-549">`true` - Insert space before a comma</span></span><br /><br /><span data-ttu-id="d1f54-550">`false` - 쉼표 앞에서 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-550">`false` - Remove space before a comma</span></span> |

<span data-ttu-id="d1f54-551">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-551">Code examples:</span></span>

```csharp
// csharp_space_before_comma = true
int[] x = new int[] { 1 , 2 , 3 , 4 , 5 };

// csharp_space_before_comma = false
int[] x = new int[] { 1, 2, 3, 4, 5 };
```

#### <a name="csharp_space_after_dot"></a><span data-ttu-id="d1f54-552">csharp_space_after_dot</span><span class="sxs-lookup"><span data-stu-id="d1f54-552">csharp_space_after_dot</span></span>

|<span data-ttu-id="d1f54-553">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-553">Property</span></span>|<span data-ttu-id="d1f54-554">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-554">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-555">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-555">**Option name**</span></span> | <span data-ttu-id="d1f54-556">csharp_space_after_dot</span><span class="sxs-lookup"><span data-stu-id="d1f54-556">csharp_space_after_dot</span></span> |
| <span data-ttu-id="d1f54-557">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-557">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-558">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-558">C#</span></span> |
| <span data-ttu-id="d1f54-559">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-559">**Option values**</span></span> | <span data-ttu-id="d1f54-560">`true` - 점 뒤에 공백을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-560">`true` - Insert space after a dot</span></span><br /><br /><span data-ttu-id="d1f54-561">`false` - 점 뒤의 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-561">`false` - Remove space after a dot</span></span> |

<span data-ttu-id="d1f54-562">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-562">Code examples:</span></span>

```csharp
// csharp_space_after_dot = true
this. Goo();

// csharp_space_after_dot = false
this.Goo();
```

#### <a name="csharp_space_before_dot"></a><span data-ttu-id="d1f54-563">csharp_space_before_dot</span><span class="sxs-lookup"><span data-stu-id="d1f54-563">csharp_space_before_dot</span></span>

|<span data-ttu-id="d1f54-564">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-564">Property</span></span>|<span data-ttu-id="d1f54-565">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-565">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-566">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-566">**Option name**</span></span> | <span data-ttu-id="d1f54-567">csharp_space_before_dot</span><span class="sxs-lookup"><span data-stu-id="d1f54-567">csharp_space_before_dot</span></span> |
| <span data-ttu-id="d1f54-568">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-568">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-569">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-569">C#</span></span> |
| <span data-ttu-id="d1f54-570">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-570">**Option values**</span></span> | <span data-ttu-id="d1f54-571">`true` - 점 앞에 공백을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-571">`true` - Insert space before a dot</span></span> <br /><br /><span data-ttu-id="d1f54-572">`false` - 점 앞에서 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-572">`false` - Remove space before a dot</span></span> |

<span data-ttu-id="d1f54-573">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-573">Code examples:</span></span>

```csharp
// csharp_space_before_dot = true
this .Goo();

// csharp_space_before_dot = false
this.Goo();
```

#### <a name="csharp_space_after_semicolon_in_for_statement"></a><span data-ttu-id="d1f54-574">csharp_space_after_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="d1f54-574">csharp_space_after_semicolon_in_for_statement</span></span>

|<span data-ttu-id="d1f54-575">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-575">Property</span></span>|<span data-ttu-id="d1f54-576">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-576">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-577">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-577">**Option name**</span></span> | <span data-ttu-id="d1f54-578">csharp_space_after_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="d1f54-578">csharp_space_after_semicolon_in_for_statement</span></span> |
| <span data-ttu-id="d1f54-579">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-579">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-580">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-580">C#</span></span> |
| <span data-ttu-id="d1f54-581">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-581">**Option values**</span></span> | <span data-ttu-id="d1f54-582">`true` - `for` 문의 각 세미콜론 뒤에 공백을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-582">`true` - Insert space after each semicolon in a `for` statement</span></span><br /><br /><span data-ttu-id="d1f54-583">`false` - `for` 문의 각 세미콜론 뒤에서 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-583">`false` - Remove space after each semicolon in a `for` statement</span></span> |

<span data-ttu-id="d1f54-584">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-584">Code examples:</span></span>

```csharp
// csharp_space_after_semicolon_in_for_statement = true
for (int i = 0; i < x.Length; i++)

// csharp_space_after_semicolon_in_for_statement = false
for (int i = 0;i < x.Length;i++)
```

##### <a name="csharp_space_before_semicolon_in_for_statement"></a><span data-ttu-id="d1f54-585">csharp_space_before_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="d1f54-585">csharp_space_before_semicolon_in_for_statement</span></span>

|<span data-ttu-id="d1f54-586">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-586">Property</span></span>|<span data-ttu-id="d1f54-587">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-587">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-588">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-588">**Option name**</span></span> | <span data-ttu-id="d1f54-589">csharp_space_before_semicolon_in_for_statement</span><span class="sxs-lookup"><span data-stu-id="d1f54-589">csharp_space_before_semicolon_in_for_statement</span></span> |
| <span data-ttu-id="d1f54-590">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-590">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-591">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-591">C#</span></span> |
| <span data-ttu-id="d1f54-592">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-592">**Option values**</span></span> | <span data-ttu-id="d1f54-593">`true` - `for` 문의 각 세미콜론 앞에 공백을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-593">`true` - Insert space before each semicolon in a `for` statement</span></span> <br /><br /><span data-ttu-id="d1f54-594">`false` - `for` 문의 각 세미콜론 앞에서 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-594">`false` - Remove space before each semicolon in a `for` statement</span></span> |

<span data-ttu-id="d1f54-595">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-595">Code examples:</span></span>

```csharp
// csharp_space_before_semicolon_in_for_statement = true
for (int i = 0 ; i < x.Length ; i++)

// csharp_space_before_semicolon_in_for_statement = false
for (int i = 0; i < x.Length; i++)
```

#### <a name="csharp_space_around_declaration_statements"></a><span data-ttu-id="d1f54-596">csharp_space_around_declaration_statements</span><span class="sxs-lookup"><span data-stu-id="d1f54-596">csharp_space_around_declaration_statements</span></span>

|<span data-ttu-id="d1f54-597">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-597">Property</span></span>|<span data-ttu-id="d1f54-598">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-598">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-599">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-599">**Option name**</span></span> | <span data-ttu-id="d1f54-600">csharp_space_around_declaration_statements</span><span class="sxs-lookup"><span data-stu-id="d1f54-600">csharp_space_around_declaration_statements</span></span> |
| <span data-ttu-id="d1f54-601">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-601">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-602">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-602">C#</span></span> |
| <span data-ttu-id="d1f54-603">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-603">**Option values**</span></span> | <span data-ttu-id="d1f54-604">`ignore` - 선언문에서 추가 공백 문자를 제거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-604">`ignore` - Don't remove extra space characters in declaration statements</span></span><br /><br /><span data-ttu-id="d1f54-605">`false` - 선언문에서 추가 공백 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-605">`false` - Remove extra space characters in declaration statements</span></span> |

<span data-ttu-id="d1f54-606">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-606">Code examples:</span></span>

```csharp
// csharp_space_around_declaration_statements = ignore
int    x    =    0   ;

// csharp_space_around_declaration_statements = false
int x = 0;
```

#### <a name="csharp_space_before_open_square_brackets"></a><span data-ttu-id="d1f54-607">csharp_space_before_open_square_brackets</span><span class="sxs-lookup"><span data-stu-id="d1f54-607">csharp_space_before_open_square_brackets</span></span>

|<span data-ttu-id="d1f54-608">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-608">Property</span></span>|<span data-ttu-id="d1f54-609">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-609">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-610">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-610">**Option name**</span></span> | <span data-ttu-id="d1f54-611">csharp_space_before_open_square_brackets</span><span class="sxs-lookup"><span data-stu-id="d1f54-611">csharp_space_before_open_square_brackets</span></span> |
| <span data-ttu-id="d1f54-612">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-612">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-613">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-613">C#</span></span> |
| <span data-ttu-id="d1f54-614">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-614">**Option values**</span></span> | <span data-ttu-id="d1f54-615">`true` - 여는 대괄호 `[` 앞에 공백을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-615">`true` - Insert space before opening square brackets `[`</span></span> <br /><br /><span data-ttu-id="d1f54-616">`false` - 여는 대괄호 `[` 앞에서 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-616">`false` - Remove space before opening square brackets `[`</span></span> |

<span data-ttu-id="d1f54-617">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-617">Code examples:</span></span>

```csharp
// csharp_space_before_open_square_brackets = true
int [] numbers = new int [] { 1, 2, 3, 4, 5 };

// csharp_space_before_open_square_brackets = false
int[] numbers = new int[] { 1, 2, 3, 4, 5 };
```

#### <a name="csharp_space_between_empty_square_brackets"></a><span data-ttu-id="d1f54-618">csharp_space_between_empty_square_brackets</span><span class="sxs-lookup"><span data-stu-id="d1f54-618">csharp_space_between_empty_square_brackets</span></span>

|<span data-ttu-id="d1f54-619">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-619">Property</span></span>|<span data-ttu-id="d1f54-620">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-620">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-621">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-621">**Option name**</span></span> | <span data-ttu-id="d1f54-622">csharp_space_between_empty_square_brackets</span><span class="sxs-lookup"><span data-stu-id="d1f54-622">csharp_space_between_empty_square_brackets</span></span> |
| <span data-ttu-id="d1f54-623">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-623">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-624">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-624">C#</span></span> |
| <span data-ttu-id="d1f54-625">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-625">**Option values**</span></span> | <span data-ttu-id="d1f54-626">`true` - 빈 대괄호 `[ ]` 사이에 공백을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-626">`true` - Insert space between empty square brackets `[ ]`</span></span> <br /><br /><span data-ttu-id="d1f54-627">`false` - 빈 대괄호 `[]` 사이에서 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-627">`false` - Remove space between empty square brackets `[]`</span></span> |

<span data-ttu-id="d1f54-628">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-628">Code examples:</span></span>

```csharp
// csharp_space_between_empty_square_brackets = true
int[ ] numbers = new int[ ] { 1, 2, 3, 4, 5 };

// csharp_space_between_empty_square_brackets = false
int[] numbers = new int[] { 1, 2, 3, 4, 5 };
```

#### <a name="csharp_space_between_square_brackets"></a><span data-ttu-id="d1f54-629">csharp_space_between_square_brackets</span><span class="sxs-lookup"><span data-stu-id="d1f54-629">csharp_space_between_square_brackets</span></span>

|<span data-ttu-id="d1f54-630">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-630">Property</span></span>|<span data-ttu-id="d1f54-631">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-631">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-632">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-632">**Option name**</span></span> | <span data-ttu-id="d1f54-633">csharp_space_between_square_brackets</span><span class="sxs-lookup"><span data-stu-id="d1f54-633">csharp_space_between_square_brackets</span></span> |
| <span data-ttu-id="d1f54-634">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-634">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-635">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-635">C#</span></span> |
| <span data-ttu-id="d1f54-636">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-636">**Option values**</span></span> | <span data-ttu-id="d1f54-637">`true` - 비어 있지 않은 대괄호 `[ 0 ]` 안에 공백 문자를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-637">`true` - Insert space characters in non-empty square brackets `[ 0 ]`</span></span> <br /><br /><span data-ttu-id="d1f54-638">`false` - 비어 있지 않은 대괄호 `[0]` 안에서 공백 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-638">`false` - Remove space characters in non-empty square brackets `[0]`</span></span> |

<span data-ttu-id="d1f54-639">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-639">Code examples:</span></span>

```csharp
// csharp_space_between_square_brackets = true
int index = numbers[ 0 ];

// csharp_space_between_square_brackets = false
int index = numbers[0];
```

### <a name="wrap-options"></a><span data-ttu-id="d1f54-640">줄 바꿈 옵션</span><span class="sxs-lookup"><span data-stu-id="d1f54-640">Wrap options</span></span>

<span data-ttu-id="d1f54-641">이러한 서식 설정 규칙은 문 및 코드 블록에 단일 줄 및 별도 줄을 사용하는 것을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-641">These formatting rules concern the use of single lines versus separate lines for statements and code blocks.</span></span>

<span data-ttu-id="d1f54-642">예제 *.editorconfig* 파일:</span><span class="sxs-lookup"><span data-stu-id="d1f54-642">Example *.editorconfig* file:</span></span>

```ini
# CSharp formatting rules:
[*.cs]
csharp_preserve_single_line_statements = true
csharp_preserve_single_line_blocks = true
```

#### <a name="csharp_preserve_single_line_statements"></a><span data-ttu-id="d1f54-643">csharp_preserve_single_line_statements</span><span class="sxs-lookup"><span data-stu-id="d1f54-643">csharp_preserve_single_line_statements</span></span>

|<span data-ttu-id="d1f54-644">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-644">Property</span></span>|<span data-ttu-id="d1f54-645">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-645">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-646">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-646">**Option name**</span></span> | <span data-ttu-id="d1f54-647">csharp_preserve_single_line_statements</span><span class="sxs-lookup"><span data-stu-id="d1f54-647">csharp_preserve_single_line_statements</span></span> |
| <span data-ttu-id="d1f54-648">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-648">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-649">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-649">C#</span></span> |
| <span data-ttu-id="d1f54-650">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-650">**Introduced version**</span></span> | <span data-ttu-id="d1f54-651">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d1f54-651">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d1f54-652">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-652">**Option values**</span></span> | <span data-ttu-id="d1f54-653">`true` - 문과 멤버 선언을 동일한 줄에 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-653">`true` - Leave statements and member declarations on the same line</span></span><br /><br /><span data-ttu-id="d1f54-654">`false` - 문과 멤버 선언을 다른 줄에 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-654">`false` - Leave statements and member declarations on different lines</span></span> |

<span data-ttu-id="d1f54-655">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-655">Code examples:</span></span>

```csharp
//csharp_preserve_single_line_statements = true
int i = 0; string name = "John";

//csharp_preserve_single_line_statements = false
int i = 0;
string name = "John";
```

#### <a name="csharp_preserve_single_line_blocks"></a><span data-ttu-id="d1f54-656">csharp_preserve_single_line_blocks</span><span class="sxs-lookup"><span data-stu-id="d1f54-656">csharp_preserve_single_line_blocks</span></span>

|<span data-ttu-id="d1f54-657">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-657">Property</span></span>|<span data-ttu-id="d1f54-658">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-658">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-659">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-659">**Option name**</span></span> | <span data-ttu-id="d1f54-660">csharp_preserve_single_line_blocks</span><span class="sxs-lookup"><span data-stu-id="d1f54-660">csharp_preserve_single_line_blocks</span></span> |
| <span data-ttu-id="d1f54-661">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-661">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-662">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-662">C#</span></span> |
| <span data-ttu-id="d1f54-663">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-663">**Introduced version**</span></span> | <span data-ttu-id="d1f54-664">Visual Studio 2017 15.3 버전</span><span class="sxs-lookup"><span data-stu-id="d1f54-664">Visual Studio 2017 version 15.3</span></span> |
| <span data-ttu-id="d1f54-665">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-665">**Option values**</span></span> | <span data-ttu-id="d1f54-666">`true` - 코드 블록을 한 줄에 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-666">`true` - Leave code block on single line</span></span><br /><br /><span data-ttu-id="d1f54-667">`false` - 코드 블록을 새 줄에 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-667">`false` - Leave code block on separate lines</span></span> |

<span data-ttu-id="d1f54-668">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-668">Code examples:</span></span>

```csharp
//csharp_preserve_single_line_blocks = true
public int Foo { get; set; }

//csharp_preserve_single_line_blocks = false
public int MyProperty
{
    get; set;
}
```

### <a name="using-directive-options"></a><span data-ttu-id="d1f54-669">지시문 옵션 사용</span><span class="sxs-lookup"><span data-stu-id="d1f54-669">Using directive options</span></span>

<span data-ttu-id="d1f54-670">이 서식 지정 규칙은 네임스페이스 내부에 배치거나 외부에 배치되는 지시문을 사용하는 것과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f54-670">This formatting rule concerns the use of using directives being placed inside versus outside a namespace.</span></span>

<span data-ttu-id="d1f54-671">예제 *.editorconfig* 파일:</span><span class="sxs-lookup"><span data-stu-id="d1f54-671">Example *.editorconfig* file:</span></span>

```ini
# 'using' directive preferences
[*.cs]
csharp_using_directive_placement = outside_namespace
csharp_using_directive_placement = inside_namespace
```

#### <a name="csharp_using_directive_placement"></a><span data-ttu-id="d1f54-672">csharp_using_directive_placement</span><span class="sxs-lookup"><span data-stu-id="d1f54-672">csharp_using_directive_placement</span></span>

|<span data-ttu-id="d1f54-673">속성</span><span class="sxs-lookup"><span data-stu-id="d1f54-673">Property</span></span>|<span data-ttu-id="d1f54-674">값</span><span class="sxs-lookup"><span data-stu-id="d1f54-674">Value</span></span>|
|-|-|
| <span data-ttu-id="d1f54-675">**옵션 이름**</span><span class="sxs-lookup"><span data-stu-id="d1f54-675">**Option name**</span></span> | <span data-ttu-id="d1f54-676">csharp_using_directive_placement</span><span class="sxs-lookup"><span data-stu-id="d1f54-676">csharp_using_directive_placement</span></span> |
| <span data-ttu-id="d1f54-677">**해당 언어**</span><span class="sxs-lookup"><span data-stu-id="d1f54-677">**Applicable languages**</span></span> | <span data-ttu-id="d1f54-678">C#</span><span class="sxs-lookup"><span data-stu-id="d1f54-678">C#</span></span> |
| <span data-ttu-id="d1f54-679">**도입된 버전**</span><span class="sxs-lookup"><span data-stu-id="d1f54-679">**Introduced version**</span></span> | <span data-ttu-id="d1f54-680">Visual Studio 2019 버전 16.1</span><span class="sxs-lookup"><span data-stu-id="d1f54-680">Visual Studio 2019 version 16.1</span></span> |
| <span data-ttu-id="d1f54-681">**옵션 값**</span><span class="sxs-lookup"><span data-stu-id="d1f54-681">**Option values**</span></span> | <span data-ttu-id="d1f54-682">`outside_namespace` - 네임스페이스 외부에서 지시문을 사용</span><span class="sxs-lookup"><span data-stu-id="d1f54-682">`outside_namespace` - Leave using directives outside namespace</span></span><br /><br /><span data-ttu-id="d1f54-683">`inside_namespace` - 네임스페이스 내부에서 지시문을 사용</span><span class="sxs-lookup"><span data-stu-id="d1f54-683">`inside_namespace` - Leave using directives inside namespace</span></span> |

<span data-ttu-id="d1f54-684">코드 예제:</span><span class="sxs-lookup"><span data-stu-id="d1f54-684">Code examples:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="d1f54-685">참조</span><span class="sxs-lookup"><span data-stu-id="d1f54-685">See also</span></span>

- [<span data-ttu-id="d1f54-686">언어 규칙</span><span class="sxs-lookup"><span data-stu-id="d1f54-686">Language rules</span></span>](language-rules.md)
- [<span data-ttu-id="d1f54-687">이름 지정 규칙</span><span class="sxs-lookup"><span data-stu-id="d1f54-687">Naming rules</span></span>](naming-rules.md)
- [<span data-ttu-id="d1f54-688">.NET 코드 스타일 규칙 참조</span><span class="sxs-lookup"><span data-stu-id="d1f54-688">.NET code style rules reference</span></span>](index.md)
