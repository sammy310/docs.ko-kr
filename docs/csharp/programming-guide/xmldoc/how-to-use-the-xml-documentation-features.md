---
title: XML 문서 기능을 사용하는 방법 - C# 프로그래밍 가이드
ms.date: 06/01/2018
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
ms.openlocfilehash: 57034fb835d4c82b5bf658e61ec78ef226c2551e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789780"
---
# <a name="how-to-use-the-xml-documentation-features"></a><span data-ttu-id="20229-102">XML 문서 기능을 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="20229-102">How to use the XML documentation features</span></span>

<span data-ttu-id="20229-103">다음 샘플은 문서화된 형식에 대한 기본 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="20229-103">The following sample provides a basic overview of a type that has been documented.</span></span>

## <a name="example"></a><span data-ttu-id="20229-104">예제</span><span class="sxs-lookup"><span data-stu-id="20229-104">Example</span></span>

[!code-csharp[csProgGuideDocComments#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#15)]

<span data-ttu-id="20229-105">이 예제에서는 다음 내용과 같은 내용의 *.xml* 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="20229-105">The example generates an *.xml* file with the following contents.</span></span>

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

## <a name="compiling-the-code"></a><span data-ttu-id="20229-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="20229-106">Compiling the code</span></span>

<span data-ttu-id="20229-107">예제를 컴파일하려면 다음 명령줄을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="20229-107">To compile the example, type the following command line:</span></span>

`csc XMLsample.cs /doc:XMLsample.xml`

<span data-ttu-id="20229-108">이 명령으로 TYPE 명령을 사용하거나 브라우저에서 볼 수 있는 XML 파일 *XMLsample.xml*이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="20229-108">This command creates the XML file *XMLsample.xml*, which you can view in your browser or by using the TYPE command.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="20229-109">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="20229-109">Robust programming</span></span>

<span data-ttu-id="20229-110">XML 문서는 ///로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="20229-110">XML documentation starts with ///.</span></span> <span data-ttu-id="20229-111">새 프로젝트를 만드는 경우 마법사에서 몇 개의 시작 /// 줄을 자동으로 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="20229-111">When you create a new project, the wizards put some starter /// lines in for you.</span></span> <span data-ttu-id="20229-112">이러한 주석의 처리에는 몇 가지 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20229-112">The processing of these comments has some restrictions:</span></span>

- <span data-ttu-id="20229-113">문서는 잘 구성된 XML이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20229-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="20229-114">XML이 잘 구성되지 않은 경우 경고가 생성되고, 문서 파일에 오류가 발생했다는 주석이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="20229-114">If the XML is not well-formed, a warning is generated and the documentation file will contain a comment that says that an error was encountered.</span></span>

- <span data-ttu-id="20229-115">개발자는 각자 고유한 태그 집합을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20229-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="20229-116">[권장 태그 집합](recommended-tags-for-documentation-comments.md)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20229-116">There is a [recommended set of tags](recommended-tags-for-documentation-comments.md).</span></span> <span data-ttu-id="20229-117">권장 태그 중 일부는 특별한 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20229-117">Some of the recommended tags have special meanings:</span></span>

  - <span data-ttu-id="20229-118">\<param> 태그는 매개 변수를 설명하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="20229-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="20229-119">사용되는 경우 컴파일러는 매개 변수가 있고 모든 매개 변수가 문서에서 설명되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="20229-119">If used, the compiler verifies that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="20229-120">확인에 실패하면 컴파일러가 경고를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="20229-120">If the verification failed, the compiler issues a warning.</span></span>

  - <span data-ttu-id="20229-121">`cref` 특성을 태그에 연결하여 코드 요소에 대한 참조를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20229-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="20229-122">컴파일러에서 이 코드 요소가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="20229-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="20229-123">확인에 실패하면 컴파일러가 경고를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="20229-123">If the verification failed, the compiler issues a warning.</span></span> <span data-ttu-id="20229-124">컴파일러는 `cref` 특성에 설명된 형식을 찾을 때 모든 `using` 문을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="20229-124">The compiler respects any `using` statements when it looks for a type described in the `cref` attribute.</span></span>

  - <span data-ttu-id="20229-125">\<summary> 태그는 Visual Studio 내의 IntelliSense에서 형식 또는 멤버에 대한 추가 정보를 표시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="20229-125">The \<summary> tag is used by IntelliSense inside Visual Studio to display additional information about a type or member.</span></span>

    > [!NOTE]
    > <span data-ttu-id="20229-126">XML 파일은 형식 및 멤버에 대한 전체 정보를 제공하지 않습니다(예: 형식 정보가 포함되지 않음).</span><span class="sxs-lookup"><span data-stu-id="20229-126">The XML file does not provide full information about the type and members (for example, it does not contain any type information).</span></span> <span data-ttu-id="20229-127">형식 또는 멤버에 대한 전체 정보를 가져오려면 실제 형식 또는 멤버에 대한 리플렉션과 함께 문서 파일을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20229-127">To get full information about a type or member, the documentation file must be used together with reflection on the actual type or member.</span></span>

## <a name="see-also"></a><span data-ttu-id="20229-128">참조</span><span class="sxs-lookup"><span data-stu-id="20229-128">See also</span></span>

- [<span data-ttu-id="20229-129">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="20229-129">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="20229-130">-doc(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="20229-130">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="20229-131">XML 문서 주석</span><span class="sxs-lookup"><span data-stu-id="20229-131">XML documentation comments</span></span>](./index.md)
- [<span data-ttu-id="20229-132">DocFX 설명서 프로세서</span><span class="sxs-lookup"><span data-stu-id="20229-132">DocFX documentation processor</span></span>](https://dotnet.github.io/docfx/)
- [<span data-ttu-id="20229-133">Sandcastle 설명서 프로세서</span><span class="sxs-lookup"><span data-stu-id="20229-133">Sandcastle documentation processor</span></span>](https://github.com/EWSoftware/SHFB)
