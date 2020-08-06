---
title: <include> - C# 프로그래밍 가이드
description: XML <include> 태그에 대해 알아봅니다. 이 태그를 사용하면 소스 코드의 형식과 멤버를 설명하는 다른 파일의 주석을 참조할 수 있습니다.
ms.date: 07/20/2015
f1_keywords:
- include
- <include>
helpviewer_keywords:
- <include> C# XML tag
- include C# XML tag
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
ms.openlocfilehash: 15a99444d464594cc91a7c8805c564c703c3b608
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381907"
---
# <a name="include-c-programming-guide"></a><span data-ttu-id="7bf28-105">\<include>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="7bf28-105">\<include> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="7bf28-106">구문</span><span class="sxs-lookup"><span data-stu-id="7bf28-106">Syntax</span></span>

```xml
<include file='filename' path='tagpath[@name="id"]' />
```

## <a name="parameters"></a><span data-ttu-id="7bf28-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7bf28-107">Parameters</span></span>

- `filename`

  <span data-ttu-id="7bf28-108">문서가 포함된 XML 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf28-108">The name of the XML file containing the documentation.</span></span> <span data-ttu-id="7bf28-109">파일 이름은 소스 코드 파일에 상대 경로로 한정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bf28-109">The file name can be qualified with a path relative to the source code file.</span></span> <span data-ttu-id="7bf28-110">`filename`을 작은따옴표(‘ ’)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="7bf28-110">Enclose `filename` in single quotation marks (' ').</span></span>

- `tagpath`

  <span data-ttu-id="7bf28-111">`filename`의 태그 경로로, `name` 태그에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bf28-111">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="7bf28-112">경로를 작은따옴표(‘ ’)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="7bf28-112">Enclose the path in single quotation marks (' ').</span></span>

- `name`

  <span data-ttu-id="7bf28-113">주석 앞에 오는 태그의 이름 지정자입니다. `name`에는 `id`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bf28-113">The name specifier in the tag that precedes the comments; `name` will have an `id`.</span></span>

- `id`

<span data-ttu-id="7bf28-114">주석 앞에 오는 태그의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf28-114">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="7bf28-115">ID를 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="7bf28-115">Enclose the ID in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="7bf28-116">설명</span><span class="sxs-lookup"><span data-stu-id="7bf28-116">Remarks</span></span>

<span data-ttu-id="7bf28-117">`<include>` 태그를 사용하면 소스 코드의 형식과 멤버를 설명하는 다른 파일의 주석을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bf28-117">The `<include>` tag lets you refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="7bf28-118">소스 코드 파일에 직접 문서 주석을 포함하는 대신 사용되는 대안입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf28-118">This is an alternative to placing documentation comments directly in your source code file.</span></span> <span data-ttu-id="7bf28-119">별도 파일에 문서를 배치하면 소스 코드와 별도로 문서에 소스 제어를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bf28-119">By putting the documentation in a separate file, you can apply source control to the documentation separately from the source code.</span></span> <span data-ttu-id="7bf28-120">한 사람은 소스 코드 파일을 체크 아웃하고 다른 사람은 문서 파일을 체크 아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bf28-120">One person can have the source code file checked out and someone else can have the documentation file checked out.</span></span>

<span data-ttu-id="7bf28-121">`<include>` 태그는 XML XPath 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7bf28-121">The `<include>` tag uses the XML XPath syntax.</span></span> <span data-ttu-id="7bf28-122">`<include>` 사용을 사용자 지정하는 방법은 XPath 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7bf28-122">Refer to XPath documentation for ways to customize your `<include>` use.</span></span>

## <a name="example"></a><span data-ttu-id="7bf28-123">예제</span><span class="sxs-lookup"><span data-stu-id="7bf28-123">Example</span></span>

<span data-ttu-id="7bf28-124">다중 파일 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf28-124">This is a multifile example.</span></span> <span data-ttu-id="7bf28-125">다음은 `<include>` 태그를 사용하는 첫 번째 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf28-125">The following is the first file, which uses `<include>`.</span></span>

[!code-csharp[csProgGuideDocComments#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#5)]

<span data-ttu-id="7bf28-126">두 번째 파일인 *xml_include_tag.doc*에는 다음과 같은 문서 주석이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bf28-126">The second file, *xml_include_tag.doc*, contains the following documentation comments.</span></span>

```xml
<MyDocs>

<MyMembers name="test">
<summary>
The summary for this type.
</summary>
</MyMembers>

<MyMembers name="test2">
<summary>
The summary for this other type.
</summary>
</MyMembers>

</MyDocs>
```

## <a name="program-output"></a><span data-ttu-id="7bf28-127">프로그램 출력</span><span class="sxs-lookup"><span data-stu-id="7bf28-127">Program output</span></span>

<span data-ttu-id="7bf28-128">다음 명령줄을 사용하여 테스트 및 Test2 클래스를 컴파일하는 경우 다음 출력이 생성됩니다. `-doc:DocFileName.xml.` Visual Studio에서 프로젝트 디자이너의 빌드 창에 XML 문서 주석 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7bf28-128">The following output is generated when you compile the Test and Test2 classes with the following command line: `-doc:DocFileName.xml.` In Visual Studio, you specify the XML doc comments option in the Build pane of the Project Designer.</span></span> <span data-ttu-id="7bf28-129">C# 컴파일러는 `<include>` 태그를 발견할 경우 현재 소스 파일 대신 *xml_include_tag.doc*에서 문서 주석을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7bf28-129">When the C# compiler sees the `<include>` tag, it searches for documentation comments in *xml_include_tag.doc* instead of the current source file.</span></span> <span data-ttu-id="7bf28-130">그런 다음 컴파일러는 *DocFileName.xml*을 생성합니다. 이 파일은 [Sandcastle](https://github.com/EWSoftware/SHFB) 등의 문서 도구에서 최종 문서를 생성하는 데 사용하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="7bf28-130">The compiler then generates *DocFileName.xml*, and this is the file that is consumed by documentation tools such as [Sandcastle](https://github.com/EWSoftware/SHFB) to produce the final documentation.</span></span>  
  
```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>xml_include_tag</name>
    </assembly>
    <members>
        <member name="T:Test">
            <summary>
The summary for this type.
</summary>
        </member>
        <member name="T:Test2">
            <summary>
The summary for this other type.
</summary>
        </member>
    </members>
</doc>
```  
  
## <a name="see-also"></a><span data-ttu-id="7bf28-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7bf28-131">See also</span></span>

- [<span data-ttu-id="7bf28-132">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="7bf28-132">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="7bf28-133">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="7bf28-133">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
