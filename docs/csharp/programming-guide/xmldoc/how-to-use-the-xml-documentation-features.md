---
title: XML 문서 기능을 사용하는 방법 - C# 프로그래밍 가이드
description: XML 문서 기능을 사용하는 방법을 알아봅니다. 코드 예제를 살펴보고 사용 가능한 추가 리소스를 확인합니다.
ms.date: 06/01/2018
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
ms.openlocfilehash: 9ad2cfe62c70174eec9020ad4c8ce11608aca36d
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380672"
---
# <a name="how-to-use-the-xml-documentation-features"></a><span data-ttu-id="b8f6e-104">XML 문서 기능을 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="b8f6e-104">How to use the XML documentation features</span></span>

<span data-ttu-id="b8f6e-105">다음 샘플은 문서화된 형식에 대한 기본 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f6e-105">The following sample provides a basic overview of a type that has been documented.</span></span>

## <a name="example"></a><span data-ttu-id="b8f6e-106">예제</span><span class="sxs-lookup"><span data-stu-id="b8f6e-106">Example</span></span>

[!code-csharp[csProgGuideDocComments#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#15)]

<span data-ttu-id="b8f6e-107">이 예제에서는 다음 내용과 같은 내용의 *.xml* 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f6e-107">The example generates an *.xml* file with the following contents.</span></span>

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>xmlsample</name>
    </assembly>
    <members>
        <member name="T:TestClass">
            <summary>
            Class level summary documentation goes here.
            </summary>
            <remarks>
            Longer comments can be associated with a type or member through
            the remarks tag.
            </remarks>
        </member>
        <member name="F:TestClass._name">
            <summary>
            Store for the Name property.
            </summary>
        </member>
        <member name="M:TestClass.#ctor">
            <summary>
            The class constructor.
            </summary>
        </member>
        <member name="P:TestClass.Name">
            <summary>
            Name property.
            </summary>
            <value>
            A value tag is used to describe the property value.
            </value>
        </member>
        <member name="M:TestClass.SomeMethod(System.String)">
            <summary>
            Description for SomeMethod.
            </summary>
            <param name="s"> Parameter description for s goes here.</param>
            <seealso cref="T:System.String">
            You can use the cref attribute on any tag to reference a type or member
            and the compiler will check that the reference exists.
            </seealso>
        </member>
        <member name="M:TestClass.SomeOtherMethod">
            <summary>
            Some other method.
            </summary>
            <returns>
            Return values are described through the returns tag.
            </returns>
            <seealso cref="M:TestClass.SomeMethod(System.String)">
            Notice the use of the cref attribute to reference a specific method.
            </seealso>
        </member>
        <member name="M:TestClass.Main(System.String[])">
            <summary>
            The entry point for the application.
            </summary>
            <param name="args"> A list of command line arguments.</param>
        </member>
        <member name="T:TestInterface">
            <summary>
            Documentation that describes the interface goes here.
            </summary>
            <remarks>
            Details about the interface go here.
            </remarks>
        </member>
        <member name="M:TestInterface.InterfaceMethod(System.Int32)">
            <summary>
            Documentation that describes the method goes here.
            </summary>
            <param name="n">
            Parameter n requires an integer argument.
            </param>
            <returns>
            The method returns an integer.
            </returns>
        </member>
    </members>
</doc>
```

## <a name="compiling-the-code"></a><span data-ttu-id="b8f6e-108">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="b8f6e-108">Compiling the code</span></span>

<span data-ttu-id="b8f6e-109">예제를 컴파일하려면 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f6e-109">To compile the example, enter the following command:</span></span>

`csc XMLsample.cs /doc:XMLsample.xml`

<span data-ttu-id="b8f6e-110">이 명령으로 `TYPE` 명령을 사용하거나 브라우저에서 볼 수 있는 XML 파일 *XMLsample.xml*이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8f6e-110">This command creates the XML file *XMLsample.xml*, which you can view in your browser or by using the `TYPE` command.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="b8f6e-111">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="b8f6e-111">Robust programming</span></span>

<span data-ttu-id="b8f6e-112">XML 문서는 `///`로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f6e-112">XML documentation starts with `///`.</span></span> <span data-ttu-id="b8f6e-113">새 프로젝트를 만드는 경우 마법사에서 몇 개의 시작 `///` 줄을 자동으로 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b8f6e-113">When you create a new project, the wizards put some starter `///` lines in for you.</span></span> <span data-ttu-id="b8f6e-114">이러한 주석의 처리에는 몇 가지 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8f6e-114">The processing of these comments has some restrictions:</span></span>

- <span data-ttu-id="b8f6e-115">문서는 잘 구성된 XML이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f6e-115">The documentation must be well-formed XML.</span></span> <span data-ttu-id="b8f6e-116">XML이 잘 구성되지 않은 경우 경고가 생성되고, 문서 파일에 오류가 발생했다는 주석이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8f6e-116">If the XML is not well-formed, a warning is generated and the documentation file will contain a comment that says that an error was encountered.</span></span>

- <span data-ttu-id="b8f6e-117">개발자는 각자 고유한 태그 집합을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8f6e-117">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="b8f6e-118">[권장 태그 집합](recommended-tags-for-documentation-comments.md)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8f6e-118">There is a [recommended set of tags](recommended-tags-for-documentation-comments.md).</span></span> <span data-ttu-id="b8f6e-119">권장 태그 중 일부는 특별한 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8f6e-119">Some of the recommended tags have special meanings:</span></span>

  - <span data-ttu-id="b8f6e-120">`<param>` 태그는 매개 변수를 설명하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8f6e-120">The `<param>` tag is used to describe parameters.</span></span> <span data-ttu-id="b8f6e-121">사용되는 경우 컴파일러는 매개 변수가 있고 모든 매개 변수가 문서에서 설명되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f6e-121">If used, the compiler verifies that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="b8f6e-122">확인에 실패하면 컴파일러가 경고를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f6e-122">If the verification fails, the compiler issues a warning.</span></span>

  - <span data-ttu-id="b8f6e-123">`cref` 특성을 태그에 연결하여 코드 요소를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8f6e-123">The `cref` attribute can be attached to any tag to reference a code element.</span></span> <span data-ttu-id="b8f6e-124">컴파일러에서 이 코드 요소가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f6e-124">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="b8f6e-125">확인에 실패하면 컴파일러가 경고를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b8f6e-125">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="b8f6e-126">컴파일러는 `cref` 특성에 설명된 형식을 찾을 때 모든 `using` 문을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b8f6e-126">The compiler respects any `using` statements when it looks for a type described in the `cref` attribute.</span></span>

  - <span data-ttu-id="b8f6e-127">`<summary>` 태그는 Visual Studio 내의 IntelliSense에서 형식 또는 멤버에 대한 추가 정보를 표시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8f6e-127">The `<summary>` tag is used by IntelliSense inside Visual Studio to display additional information about a type or member.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b8f6e-128">XML 파일은 형식 및 멤버에 대한 전체 정보를 제공하지 않습니다(예: 형식 정보가 포함되지 않음).</span><span class="sxs-lookup"><span data-stu-id="b8f6e-128">The XML file does not provide full information about the type and members (for example, it does not contain any type information).</span></span> <span data-ttu-id="b8f6e-129">형식 또는 멤버에 대한 전체 정보를 가져오려면 실제 형식 또는 멤버에 대한 리플렉션과 함께 문서 파일을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="b8f6e-129">To get full information about a type or member, use the documentation file together with reflection on the actual type or member.</span></span>

## <a name="see-also"></a><span data-ttu-id="b8f6e-130">참조</span><span class="sxs-lookup"><span data-stu-id="b8f6e-130">See also</span></span>

- [<span data-ttu-id="b8f6e-131">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="b8f6e-131">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="b8f6e-132">-doc(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="b8f6e-132">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="b8f6e-133">XML 문서 주석</span><span class="sxs-lookup"><span data-stu-id="b8f6e-133">XML documentation comments</span></span>](./index.md)
- [<span data-ttu-id="b8f6e-134">DocFX 설명서 프로세서</span><span class="sxs-lookup"><span data-stu-id="b8f6e-134">DocFX documentation processor</span></span>](https://dotnet.github.io/docfx/)
- [<span data-ttu-id="b8f6e-135">Sandcastle 설명서 프로세서</span><span class="sxs-lookup"><span data-stu-id="b8f6e-135">Sandcastle documentation processor</span></span>](https://github.com/EWSoftware/SHFB)
