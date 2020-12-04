---
title: .NET 코드 스타일 규칙 옵션
description: .NET 코드 스타일 옵션을 지정 하는 방법에 대해 알아봅니다.
ms.date: 09/25/2020
ms.topic: conceptual
author: gewarren
ms.author: gewarren
ms.openlocfilehash: 5e4d80ec55f7fbcd01e364bb2b9e2b4f49f820d5
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "96593794"
---
# <a name="code-style-rule-options"></a><span data-ttu-id="66936-103">코드 스타일 규칙 옵션</span><span class="sxs-lookup"><span data-stu-id="66936-103">Code style rule options</span></span>

<span data-ttu-id="66936-104">[Editorconfig](/visualstudio/ide/create-portable-custom-editor-options) 파일에서 .net 코드 스타일 규칙 옵션을 정의 하 여 코드 베이스에서 일관 된 *코드 스타일* 을 정의 하 고 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66936-104">You can define and maintain consistent *code style* in your codebase by defining .NET code style rule options in an [EditorConfig](/visualstudio/ide/create-portable-custom-editor-options) file.</span></span> <span data-ttu-id="66936-105">이러한 규칙은 코드를 편집할 때 Visual Studio와 같은 다양 한 개발 Ide에 의해 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66936-105">These rules are surfaced by various development IDEs, such as Visual Studio, as you edit your code.</span></span> <span data-ttu-id="66936-106">.NET 프로젝트의 경우 [빌드 시](overview.md#code-style-analysis)이러한 규칙이 적용 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66936-106">For .NET projects, these rules can also be [enforced at build time](overview.md#code-style-analysis).</span></span> <span data-ttu-id="66936-107">개별 규칙을 사용 하거나 사용 하지 않도록 설정 하 고, 심각도 수준을 통해 각 규칙을 적용 하려는 수준을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66936-107">You can enable or disable individual rules and configure the degree to which you want each rule enforced, via a severity level.</span></span>

> [!TIP]
>
> - <span data-ttu-id="66936-108">EditorConfig 파일에서 코드 스타일 옵션을 정의 하는 경우 코드 [스타일 분석기](overview.md#code-style-analysis) 에서 코드를 분석 하는 방법을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="66936-108">When you define code style options in an EditorConfig file, you're configuring how you want the [code style analyzers](overview.md#code-style-analysis) to analyze your code.</span></span> <span data-ttu-id="66936-109">EditorConfig 파일은 이러한 분석기의 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="66936-109">The EditorConfig file is the configuration file for these analyzers.</span></span>
>
> - <span data-ttu-id="66936-110">[텍스트 편집기 옵션](/visualstudio/ide/code-styles-and-code-cleanup) 대화 상자에서 Visual Studio의 코드 스타일 옵션을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66936-110">Code style options can also be set in Visual Studio in the [Text editor options](/visualstudio/ide/code-styles-and-code-cleanup) dialog.</span></span> <span data-ttu-id="66936-111">이러한 옵션은 Visual Studio에서 편집 하는 동안에만 적용 되는 사용자별 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="66936-111">These are per-user options that are only respected while editing in Visual Studio.</span></span> <span data-ttu-id="66936-112">이러한 옵션은 빌드 시 또는 다른 Ide에서 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66936-112">These options are not respected at build time or by other IDEs.</span></span> <span data-ttu-id="66936-113">또한 Visual Studio 내에서 열린 프로젝트 또는 솔루션에 EditorConfig 파일이 있는 경우 EditorConfig 파일의 옵션이 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66936-113">Additionally, if the project or solution opened inside Visual Studio has an EditorConfig file, then options from the EditorConfig file take precedence.</span></span>

<span data-ttu-id="66936-114">코드 스타일 규칙은 다음 하위 범주로 나뉩니다.</span><span class="sxs-lookup"><span data-stu-id="66936-114">Code style rules are divided into following subcategories:</span></span>

- [<span data-ttu-id="66936-115">언어 규칙</span><span class="sxs-lookup"><span data-stu-id="66936-115">Language rules</span></span>](style-rules/language-rules.md)

- [<span data-ttu-id="66936-116">불필요한 코드 규칙</span><span class="sxs-lookup"><span data-stu-id="66936-116">Unnecessary code rules</span></span>](style-rules/unnecessary-code-rules.md)

- [<span data-ttu-id="66936-117">서식 지정 규칙</span><span class="sxs-lookup"><span data-stu-id="66936-117">Formatting rules</span></span>](style-rules/formatting-rules.md)

- [<span data-ttu-id="66936-118">이름 지정 규칙</span><span class="sxs-lookup"><span data-stu-id="66936-118">Naming rules</span></span>](style-rules/naming-rules.md)

<span data-ttu-id="66936-119">이러한 각 하위 범주는 옵션을 지정 하기 위한 자체 구문을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="66936-119">Each of these subcategories defines its own syntax for specifying options.</span></span> <span data-ttu-id="66936-120">이러한 규칙과 해당 옵션에 대 한 자세한 내용은 [코드 스타일 규칙 참조](style-rules/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66936-120">For more information about these rules and the corresponding options, see [Code style rule reference](style-rules/index.md).</span></span>

## <a name="example-editorconfig-file"></a><span data-ttu-id="66936-121">예제 EditorConfig 파일</span><span class="sxs-lookup"><span data-stu-id="66936-121">Example EditorConfig file</span></span>

<span data-ttu-id="66936-122">다음은 시작하는 데 도움이 되는 기본 옵션의 예제 *.editorconfig* 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="66936-122">To help you get started, here is an example *.editorconfig* file with the default options.</span></span>

> [!TIP]
> <span data-ttu-id="66936-123">Visual Studio에서 이 파일을 생성하고 **도구** > **옵션** > **텍스트 편집기** > [**C#** 또는 **기본**] > **코드 스타일** > **일반** 에서 프로젝트에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66936-123">In Visual Studio, you can generate this file and save it to a project at **Tools** > **Options** > **Text Editor** > [**C#** or  **Basic**] > **Code Style** > **General**.</span></span> <span data-ttu-id="66936-124">그런 다음 **설정에서 .editorconfig 파일 생성** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="66936-124">Then, click the **Generate .editorconfig file from settings** button.</span></span> <span data-ttu-id="66936-125">자세한 내용은 [코드 스타일 기본 설정](/visualstudio/ide/code-styles-and-code-cleanup)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66936-125">For more information, see [Code style preferences](/visualstudio/ide/code-styles-and-code-cleanup).</span></span>

```ini
# Remove the line below if you want to inherit .editorconfig settings from higher directories
root = true

# C# files
[*.cs]

#### Core EditorConfig Options ####

# Indentation and spacing
indent_size = 4
indent_style = space
tab_width = 4

# New line preferences
end_of_line = crlf
insert_final_newline = false

#### .NET Coding Conventions ####

# Organize usings
dotnet_separate_import_directive_groups = false
dotnet_sort_system_directives_first = false
file_header_template = unset

# this. and Me. preferences
dotnet_style_qualification_for_event = false:silent
dotnet_style_qualification_for_field = false:silent
dotnet_style_qualification_for_method = false:silent
dotnet_style_qualification_for_property = false:silent

# Language keywords vs BCL types preferences
dotnet_style_predefined_type_for_locals_parameters_members = true:silent
dotnet_style_predefined_type_for_member_access = true:silent

# Parentheses preferences
dotnet_style_parentheses_in_arithmetic_binary_operators = always_for_clarity:silent
dotnet_style_parentheses_in_other_binary_operators = always_for_clarity:silent
dotnet_style_parentheses_in_other_operators = never_if_unnecessary:silent
dotnet_style_parentheses_in_relational_binary_operators = always_for_clarity:silent

# Modifier preferences
dotnet_style_require_accessibility_modifiers = for_non_interface_members:silent

# Expression-level preferences
dotnet_style_coalesce_expression = true:suggestion
dotnet_style_collection_initializer = true:suggestion
dotnet_style_explicit_tuple_names = true:suggestion
dotnet_style_null_propagation = true:suggestion
dotnet_style_object_initializer = true:suggestion
dotnet_style_operator_placement_when_wrapping = beginning_of_line
dotnet_style_prefer_auto_properties = true:silent
dotnet_style_prefer_compound_assignment = true:suggestion
dotnet_style_prefer_conditional_expression_over_assignment = true:silent
dotnet_style_prefer_conditional_expression_over_return = true:silent
dotnet_style_prefer_inferred_anonymous_type_member_names = true:suggestion
dotnet_style_prefer_inferred_tuple_names = true:suggestion
dotnet_style_prefer_is_null_check_over_reference_equality_method = true:suggestion
dotnet_style_prefer_simplified_boolean_expressions = true:suggestion
dotnet_style_prefer_simplified_interpolation = true:suggestion

# Field preferences
dotnet_style_readonly_field = true:suggestion

# Parameter preferences
dotnet_code_quality_unused_parameters = all:suggestion

# Suppression preferences
dotnet_remove_unnecessary_suppression_exclusions = none

#### C# Coding Conventions ####

# var preferences
csharp_style_var_elsewhere = false:silent
csharp_style_var_for_built_in_types = false:silent
csharp_style_var_when_type_is_apparent = false:silent

# Expression-bodied members
csharp_style_expression_bodied_accessors = true:silent
csharp_style_expression_bodied_constructors = false:silent
csharp_style_expression_bodied_indexers = true:silent
csharp_style_expression_bodied_lambdas = true:silent
csharp_style_expression_bodied_local_functions = false:silent
csharp_style_expression_bodied_methods = false:silent
csharp_style_expression_bodied_operators = false:silent
csharp_style_expression_bodied_properties = true:silent

# Pattern matching preferences
csharp_style_pattern_matching_over_as_with_null_check = true:suggestion
csharp_style_pattern_matching_over_is_with_cast_check = true:suggestion
csharp_style_prefer_not_pattern = true:suggestion
csharp_style_prefer_pattern_matching = true:silent
csharp_style_prefer_switch_expression = true:suggestion

# Null-checking preferences
csharp_style_conditional_delegate_call = true:suggestion

# Modifier preferences
csharp_prefer_static_local_function = true:suggestion
csharp_preferred_modifier_order = public,private,protected,internal,static,extern,new,virtual,abstract,sealed,override,readonly,unsafe,volatile,async:silent

# Code-block preferences
csharp_prefer_braces = true:silent
csharp_prefer_simple_using_statement = true:suggestion

# Expression-level preferences
csharp_prefer_simple_default_expression = true:suggestion
csharp_style_deconstructed_variable_declaration = true:suggestion
csharp_style_inlined_variable_declaration = true:suggestion
csharp_style_pattern_local_over_anonymous_function = true:suggestion
csharp_style_prefer_index_operator = true:suggestion
csharp_style_prefer_range_operator = true:suggestion
csharp_style_throw_expression = true:suggestion
csharp_style_unused_value_assignment_preference = discard_variable:suggestion
csharp_style_unused_value_expression_statement_preference = discard_variable:silent

# 'using' directive preferences
csharp_using_directive_placement = inside_namespace:silent

#### C# Formatting Rules ####

# New line preferences
csharp_new_line_before_catch = true
csharp_new_line_before_else = true
csharp_new_line_before_finally = true
csharp_new_line_before_members_in_anonymous_types = true
csharp_new_line_before_members_in_object_initializers = true
csharp_new_line_before_open_brace = all
csharp_new_line_between_query_expression_clauses = true

# Indentation preferences
csharp_indent_block_contents = true
csharp_indent_braces = false
csharp_indent_case_contents = true
csharp_indent_case_contents_when_block = true
csharp_indent_labels = one_less_than_current
csharp_indent_switch_labels = true

# Space preferences
csharp_space_after_cast = false
csharp_space_after_colon_in_inheritance_clause = true
csharp_space_after_comma = true
csharp_space_after_dot = false
csharp_space_after_keywords_in_control_flow_statements = true
csharp_space_after_semicolon_in_for_statement = true
csharp_space_around_binary_operators = before_and_after
csharp_space_around_declaration_statements = false
csharp_space_before_colon_in_inheritance_clause = true
csharp_space_before_comma = false
csharp_space_before_dot = false
csharp_space_before_open_square_brackets = false
csharp_space_before_semicolon_in_for_statement = false
csharp_space_between_empty_square_brackets = false
csharp_space_between_method_call_empty_parameter_list_parentheses = false
csharp_space_between_method_call_name_and_opening_parenthesis = false
csharp_space_between_method_call_parameter_list_parentheses = false
csharp_space_between_method_declaration_empty_parameter_list_parentheses = false
csharp_space_between_method_declaration_name_and_open_parenthesis = false
csharp_space_between_method_declaration_parameter_list_parentheses = false
csharp_space_between_parentheses = false
csharp_space_between_square_brackets = false

# Wrapping preferences
csharp_preserve_single_line_blocks = true
csharp_preserve_single_line_statements = true

#### Naming styles ####

# Naming rules

dotnet_naming_rule.interface_should_be_begins_with_i.severity = suggestion
dotnet_naming_rule.interface_should_be_begins_with_i.symbols = interface
dotnet_naming_rule.interface_should_be_begins_with_i.style = begins_with_i

dotnet_naming_rule.types_should_be_pascal_case.severity = suggestion
dotnet_naming_rule.types_should_be_pascal_case.symbols = types
dotnet_naming_rule.types_should_be_pascal_case.style = pascal_case

dotnet_naming_rule.non_field_members_should_be_pascal_case.severity = suggestion
dotnet_naming_rule.non_field_members_should_be_pascal_case.symbols = non_field_members
dotnet_naming_rule.non_field_members_should_be_pascal_case.style = pascal_case

# Symbol specifications

dotnet_naming_symbols.interface.applicable_kinds = interface
dotnet_naming_symbols.interface.applicable_accessibilities = public, internal, private, protected, protected_internal, private_protected
dotnet_naming_symbols.interface.required_modifiers =

dotnet_naming_symbols.types.applicable_kinds = class, struct, interface, enum
dotnet_naming_symbols.types.applicable_accessibilities = public, internal, private, protected, protected_internal, private_protected
dotnet_naming_symbols.types.required_modifiers =

dotnet_naming_symbols.non_field_members.applicable_kinds = property, event, method
dotnet_naming_symbols.non_field_members.applicable_accessibilities = public, internal, private, protected, protected_internal, private_protected
dotnet_naming_symbols.non_field_members.required_modifiers =

# Naming styles

dotnet_naming_style.pascal_case.required_prefix =
dotnet_naming_style.pascal_case.required_suffix =
dotnet_naming_style.pascal_case.word_separator =
dotnet_naming_style.pascal_case.capitalization = pascal_case

dotnet_naming_style.begins_with_i.required_prefix = I
dotnet_naming_style.begins_with_i.required_suffix =
dotnet_naming_style.begins_with_i.word_separator =
dotnet_naming_style.begins_with_i.capitalization = pascal_case

```

## <a name="see-also"></a><span data-ttu-id="66936-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66936-126">See also</span></span>

- [<span data-ttu-id="66936-127">코드 스타일 분석 규칙 참조</span><span class="sxs-lookup"><span data-stu-id="66936-127">Code style analysis rule reference</span></span>](style-rules/index.md)
- [<span data-ttu-id="66936-128">빌드에 코드 스타일 적용</span><span class="sxs-lookup"><span data-stu-id="66936-128">Enforce code style on build</span></span>](overview.md#code-style-analysis)
- [<span data-ttu-id="66936-129">Visual Studio의 빠른 작업</span><span class="sxs-lookup"><span data-stu-id="66936-129">Quick Actions in Visual Studio</span></span>](/visualstudio/ide/quick-actions)
- [<span data-ttu-id="66936-130">Visual Studio에서 이식 가능한 사용자 지정 편집기 옵션 만들기</span><span class="sxs-lookup"><span data-stu-id="66936-130">Create portable custom editor options in Visual Studio</span></span>](/visualstudio/ide/create-portable-custom-editor-options)
- [<span data-ttu-id="66936-131">.NET Compiler Platform “Roslyn” .editorconfig 파일</span><span class="sxs-lookup"><span data-stu-id="66936-131">.NET Compiler Platform "Roslyn" .editorconfig file</span></span>](https://github.com/dotnet/roslyn/blob/master/.editorconfig)
- [<span data-ttu-id="66936-132">.NET Compiler Platform 런타임 .editorconfig 파일</span><span class="sxs-lookup"><span data-stu-id="66936-132">.NET Compiler Platform Runtime .editorconfig file</span></span>](https://github.com/dotnet/runtime/blob/master/.editorconfig)
