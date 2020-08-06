---
title: 문서 태그에 대한 구분 기호 - C# 프로그래밍 가이드
description: 문서 태그 구분 기호에 대해 알아봅니다. 구분 기호는 컴파일러에게 설명서 주석을 시작하고 종료하는 위치를 나타냅니다.
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], delimiters
- /** */ delimiters for C# documentation tags
- /// delimiter for C# documentation
ms.assetid: 9b2bdd18-4f5c-4c0b-988e-fb992e0d233e
ms.openlocfilehash: 3191e32b0ff2dbde004abaab0b699cd61fcbb150
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381985"
---
# <a name="delimiters-for-documentation-tags-c-programming-guide"></a><span data-ttu-id="1e6ee-104">문서 태그에 대한 구분 기호(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="1e6ee-104">Delimiters for documentation tags (C# programming guide)</span></span>

<span data-ttu-id="1e6ee-105">XML 문서 주석을 사용하려면 문서 주석이 시작되고 끝나는 위치를 컴파일러에 알리는 구분 기호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-105">The use of XML doc comments requires delimiters, which indicate to the compiler where a documentation comment begins and ends.</span></span> <span data-ttu-id="1e6ee-106">XML 문서 태그에 다음과 같은 종류의 구분 기호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-106">You can use the following kinds of delimiters with the XML documentation tags:</span></span>

- `///`

  <span data-ttu-id="1e6ee-107">한 줄 구분 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-107">Single-line delimiter.</span></span> <span data-ttu-id="1e6ee-108">문서 예제에 표시되고 C# 프로젝트 템플릿에 사용되는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-108">This is the form that is shown in documentation examples and used by the C# project templates.</span></span> <span data-ttu-id="1e6ee-109">구분 기호 뒤에 공백 문자가 있으면 해당 문자는 XML 출력에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-109">If there is a white space character following the delimiter, that character is not included in the XML output.</span></span>

  > [!NOTE]
  > <span data-ttu-id="1e6ee-110">코드 편집기에서 `///` 구분 기호를 입력한 후에는 Visual Studio IDE(통합 개발 환경)에서 자동으로 `<summary>` 및 `</summary>` 태그가 삽입되고 이 태그 내에서 커서가 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-110">The Visual Studio integrated development environment (IDE) automatically inserts the `<summary>` and `</summary>` tags and moves your cursor within these tags after you type the `///` delimiter in the code editor.</span></span> <span data-ttu-id="1e6ee-111">이 기능은 [옵션 대화 상자](/visualstudio/ide/reference/options-text-editor-csharp-advanced)에서 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-111">You can turn this feature on or off in the [Options dialog box](/visualstudio/ide/reference/options-text-editor-csharp-advanced).</span></span>
  
- `/** */`

  <span data-ttu-id="1e6ee-112">여러 줄 구분 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-112">Multiline delimiters.</span></span>

  <span data-ttu-id="1e6ee-113">`/** */` 구분 기호를 사용할 때 따라야 하는 몇 가지 서식 설정 규칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-113">There are some formatting rules to follow when you use the `/** */` delimiters:</span></span>
  
  - <span data-ttu-id="1e6ee-114">`/**` 구분 기호가 포함된 줄에서 줄의 나머지 부분이 공백인 경우 해당 줄은 주석에 대해 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-114">On the line that contains the `/**` delimiter, if the remainder of the line is white space, the line is not processed for comments.</span></span> <span data-ttu-id="1e6ee-115">`/**` 구분 기호 다음의 첫 번째 문자가 공백인 경우 해당 공백 문자는 무시되고 줄의 나머지 부분이 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-115">If the first character after the `/**` delimiter is white space, that white space character is ignored and the rest of the line is processed.</span></span> <span data-ttu-id="1e6ee-116">그러지 않으면 `/**` 구분 기호 다음 줄의 전체 텍스트가 주석의 일부로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-116">Otherwise, the entire text of the line after the `/**` delimiter is processed as part of the comment.</span></span>

  - <span data-ttu-id="1e6ee-117">`*/` 구분 기호가 포함된 줄에서 `*/` 구분 기호까지 공백만 있으면 해당 줄은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-117">On the line that contains the `*/` delimiter, if there is only white space up to the `*/` delimiter, that line is ignored.</span></span> <span data-ttu-id="1e6ee-118">그렇지 않으면 `*/` 구분 기호 이전 줄의 텍스트가 주석의 일부로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-118">Otherwise, the text on the line up to the `*/` delimiter is processed as part of the comment.</span></span>
  
  - <span data-ttu-id="1e6ee-119">`/**` 구분 기호로 시작하는 줄 다음 줄에 대해 컴파일러는 각 줄의 시작 부분에서 일반적인 패턴을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-119">For the lines after the one that begins with the `/**` delimiter, the compiler looks for a common pattern at the beginning of each line.</span></span> <span data-ttu-id="1e6ee-120">패턴은 선택적 공백과 별표(`*`)로 구성되고 그다음에 더 많은 선택적 공백이 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-120">The pattern can consist of optional white space and an asterisk (`*`), followed by more optional white space.</span></span> <span data-ttu-id="1e6ee-121">컴파일러가 `/**` 구분 기호나 `*/` 구분 기호로 시작되지 않는 각 줄의 시작 부분에서 일반적인 패턴을 찾으면 각 줄에 대해 해당 패턴을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-121">If the compiler finds a common pattern at the beginning of each line that does not begin with the `/**` delimiter or the `*/` delimiter, it ignores that pattern for each line.</span></span>

  <span data-ttu-id="1e6ee-122">다음 예제에서는 이러한 규칙을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-122">The following examples illustrate these rules.</span></span>

  - <span data-ttu-id="1e6ee-123">다음 주석에서 유일하게 처리되는 부분은 `<summary>`로 시작하는 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-123">The only part of the following comment that's processed is the line that begins with `<summary>`.</span></span> <span data-ttu-id="1e6ee-124">세 가지 태그 서식이 동일한 주석을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-124">The three tag formats produce the same comments.</span></span>

    ```csharp
    /** <summary>text</summary> */

    /**
    <summary>text</summary>
    */

    /**
     * <summary>text</summary>
    */
    ```

  - <span data-ttu-id="1e6ee-125">컴파일러는 두 번째 및 세 번째 줄의 시작 부분에서 "\*"의 일반적인 패턴을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-125">The compiler identifies a common pattern of " \* " at the beginning of the second and third lines.</span></span> <span data-ttu-id="1e6ee-126">이 패턴은 출력에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-126">The pattern is not included in the output.</span></span>

    ```csharp
    /**
     * <summary>
     * text </summary>*/
    ```

  - <span data-ttu-id="1e6ee-127">다음 주석에서는 세 번째 줄의 두 번째 문자가 별표가 아니기 때문에 컴파일러가 일반적인 패턴을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-127">The compiler finds no common pattern in the following comment because the second character on the third line is not an asterisk.</span></span> <span data-ttu-id="1e6ee-128">따라서 두 번째 및 세 번째 줄의 모든 텍스트가 주석의 일부로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-128">Therefore, all text on the second and third lines is processed as part of the comment.</span></span>

    ```csharp
    /**
     * <summary>
       text </summary>
    */
    ```

  - <span data-ttu-id="1e6ee-129">다음 주석에서는 두 가지로 이유로 컴파일러가 패턴을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-129">The compiler finds no pattern in the following comment for two reasons.</span></span> <span data-ttu-id="1e6ee-130">첫째, 별표 앞의 공백 수가 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-130">First, the number of spaces before the asterisk is not consistent.</span></span> <span data-ttu-id="1e6ee-131">둘째, 다섯 번째 줄이 공백과 일치하지 않는 탭으로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-131">Second, the fifth line begins with a tab, which does not match spaces.</span></span> <span data-ttu-id="1e6ee-132">따라서 두 번째 줄부터 다섯 번째 줄까지 모든 텍스트가 주석의 일부로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e6ee-132">Therefore, all text from lines two through five is processed as part of the comment.</span></span>

    <!-- markdownlint-disable MD010 -->
    ```csharp
    /**
      * <summary>
      * text
     *  text2
        *  </summary>
    */
    ```
    <!-- markdownlint-enable MD010 -->

## <a name="see-also"></a><span data-ttu-id="1e6ee-133">참조</span><span class="sxs-lookup"><span data-stu-id="1e6ee-133">See also</span></span>

- [<span data-ttu-id="1e6ee-134">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="1e6ee-134">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="1e6ee-135">XML 문서 주석</span><span class="sxs-lookup"><span data-stu-id="1e6ee-135">XML documentation comments</span></span>](./index.md)
- [<span data-ttu-id="1e6ee-136">-doc(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="1e6ee-136">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
