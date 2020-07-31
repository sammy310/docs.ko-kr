---
title: '방법: CodeDOM을 사용하여 클래스 만들기'
description: CodeDOM(코드 문서 개체 모델)을 사용하여 클래스를 만드는 방법을 설명하는 자세한 예제를 참조하세요.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Code Document Object Model, graphs
- Code Document Object Model, creating classes
- graphing with CodeDOM
- CodeDOM, creating classes
- CodeDOM, graphs
ms.assetid: 0ceb70fe-36e1-49bb-922b-e9f615c20a14
ms.openlocfilehash: 3d7151d384402dba6fbb5da8fe54621346251f7b
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865309"
---
# <a name="how-to-create-a-class-using-codedom"></a><span data-ttu-id="f64f0-103">방법: CodeDOM을 사용하여 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="f64f0-103">How to: Create a Class Using CodeDOM</span></span>
<span data-ttu-id="f64f0-104">다음 절차에서는 필드 2개, 속성 3개, 메서드, 생성자 및 진입점을 포함하는 클래스를 생성하는 CodeDOM 그래프를 만들고 컴파일하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f64f0-104">The following procedures illustrate how to create and compile a CodeDOM graph that generates a class containing two fields, three properties, a method, a constructor, and an entry point.</span></span>  
  
1. <span data-ttu-id="f64f0-105">CodeDOM 코드를 사용하여 클래스에 대한 소스 코드를 생성하는 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f64f0-105">Create a console application that will use CodeDOM code to generate the source code for a class.</span></span>  
  
     <span data-ttu-id="f64f0-106">이 예제에서 생성하는 클래스의 이름은 `Sample`이고, 생성된 코드는 SampleCode 파일의 `CodeDOMCreatedClass` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="f64f0-106">In this example, the generating class is named `Sample`, and the generated code is a class named `CodeDOMCreatedClass` in a file named SampleCode.</span></span>  
  
2. <span data-ttu-id="f64f0-107">생성하는 클래스에서 CodeDOM 그래프를 초기화하고 CodeDOM 메서드를 사용하여 생성된 클래스의 멤버, 생성자 및 진입점(`Main` 메서드)을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f64f0-107">In the generating class, initialize the CodeDOM graph and use CodeDOM methods to define the members, constructor, and entry point (`Main` method) of the generated class.</span></span>  
  
     <span data-ttu-id="f64f0-108">이 예제에서 생성된 클래스에는 필드 2개, 속성 3개, 생성자, 메서드 및 `Main` 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64f0-108">In this example, the generated class has two fields, three properties, a constructor, a method, and a `Main` method.</span></span>  
  
3. <span data-ttu-id="f64f0-109">생성하는 클래스에서 언어별 코드 공급자를 만들고 해당 <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> 메서드를 호출하여 그래프에서 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f64f0-109">In the generating class, create a language-specific code provider and call its <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method to generate the code from the graph.</span></span>  
  
4. <span data-ttu-id="f64f0-110">애플리케이션을 컴파일 및 실행하여 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f64f0-110">Compile and execute the application to generate the code.</span></span>  
  
     <span data-ttu-id="f64f0-111">이 예제에서 생성된 코드는 SampleCode 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64f0-111">In this example, the generated code is in a file named SampleCode.</span></span> <span data-ttu-id="f64f0-112">해당 코드를 컴파일 및 실행하여 샘플 출력을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f64f0-112">Compile and execute that code to see the sample output.</span></span>  
  
### <a name="to-create-the-application-that-will-execute-the-codedom-code"></a><span data-ttu-id="f64f0-113">CodeDOM 코드를 실행할 애플리케이션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="f64f0-113">To create the application that will execute the CodeDOM code</span></span>  
  
- <span data-ttu-id="f64f0-114">CodeDOM 코드를 포함하는 콘솔 애플리케이션 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f64f0-114">Create a console application class to contain the CodeDOM code.</span></span> <span data-ttu-id="f64f0-115">클래스에서 어셈블리(<xref:System.CodeDom.CodeCompileUnit>) 및 클래스(<xref:System.CodeDom.CodeTypeDeclaration>)를 참조하는 데 사용할 전역 필드를 정의하고 생성된 소스 파일의 이름을 지정한 다음 `Main` 메서드를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="f64f0-115">Define the global fields that are to be used in the class to reference the assembly (<xref:System.CodeDom.CodeCompileUnit>) and class (<xref:System.CodeDom.CodeTypeDeclaration>), specify the name of the generated source file, and declare the `Main` method.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample Main#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample Main/CS/program.cs#1)]
     [!code-vb[CodeDOM Class Sample Main#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample Main/VB/program.vb#1)]  
  
### <a name="to-initialize-the-codedom-graph"></a><span data-ttu-id="f64f0-116">CodeDOM 그래프를 초기화하려면</span><span class="sxs-lookup"><span data-stu-id="f64f0-116">To initialize the CodeDOM graph</span></span>  
  
- <span data-ttu-id="f64f0-117">콘솔 애플리케이션 클래스에 대한 생성자에서 어셈블리와 클래스를 초기화하고 적절한 선언을 CodeDOM 그래프에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f64f0-117">In the constructor for the console application class, initialize the assembly and class, and add the appropriate declarations to the CodeDOM graph.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#2)]
     [!code-vb[CodeDOM Class Sample#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#2)]  
  
### <a name="to-add-members-to-the-codedom-graph"></a><span data-ttu-id="f64f0-118">CodeDOM 그래프에 멤버를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="f64f0-118">To add members to the CodeDOM graph</span></span>  
  
- <span data-ttu-id="f64f0-119">클래스의 <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> 속성에 <xref:System.CodeDom.CodeMemberField> 개체를 추가하여 CodeDOM 그래프에 필드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f64f0-119">Add fields to the CodeDOM graph by adding <xref:System.CodeDom.CodeMemberField> objects to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#3)]
     [!code-vb[CodeDOM Class Sample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#3)]  
  
- <span data-ttu-id="f64f0-120">클래스의 <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> 속성에 <xref:System.CodeDom.CodeMemberProperty> 개체를 추가하여 CodeDOM 그래프에 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f64f0-120">Add properties to the CodeDOM graph by adding <xref:System.CodeDom.CodeMemberProperty> objects to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#4)]
     [!code-vb[CodeDOM Class Sample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#4)]  
  
- <span data-ttu-id="f64f0-121">클래스의 <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> 속성에 <xref:System.CodeDom.CodeMemberMethod> 개체를 추가하여 CodeDOM 그래프에 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f64f0-121">Add a method to the CodeDOM graph by adding a <xref:System.CodeDom.CodeMemberMethod> object to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#5)]
     [!code-vb[CodeDOM Class Sample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#5)]  
  
- <span data-ttu-id="f64f0-122">클래스의 <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> 속성에 <xref:System.CodeDom.CodeConstructor> 개체를 추가하여 CodeDOM 그래프에 생성자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f64f0-122">Add a constructor to the CodeDOM graph by adding a <xref:System.CodeDom.CodeConstructor> object to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#6)]
     [!code-vb[CodeDOM Class Sample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#6)]  
  
- <span data-ttu-id="f64f0-123">클래스의 <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> 속성에 <xref:System.CodeDom.CodeEntryPointMethod> 개체를 추가하여 CodeDOM 그래프에 진입점을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f64f0-123">Add an entry point to the CodeDOM graph by adding a <xref:System.CodeDom.CodeEntryPointMethod> object to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#7)]
     [!code-vb[CodeDOM Class Sample#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#7)]  
  
### <a name="to-generate-the-code-from-the-codedom-graph"></a><span data-ttu-id="f64f0-124">CodeDOM 그래프에서 코드를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="f64f0-124">To generate the code from the CodeDOM graph</span></span>  
  
- <span data-ttu-id="f64f0-125"><xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> 메서드를 호출하여 CodeDOM 그래프에서 소스 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f64f0-125">Generate source code from the CodeDOM graph by calling the <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#8)]
     [!code-vb[CodeDOM Class Sample#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#8)]  
  
### <a name="to-create-the-graph-and-generate-the-code"></a><span data-ttu-id="f64f0-126">그래프를 만들고 코드를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="f64f0-126">To create the graph and generate the code</span></span>  
  
1. <span data-ttu-id="f64f0-127">앞의 단계에서 만든 메서드를 첫 번째 단계에서 정의한 `Main` 메서드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f64f0-127">Add the methods created in the preceding steps to the `Main` method defined in the first step.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#9)]
     [!code-vb[CodeDOM Class Sample#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#9)]  
  
2. <span data-ttu-id="f64f0-128">생성하는 클래스를 컴파일 및 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f64f0-128">Compile and execute the generating class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f64f0-129">예제</span><span class="sxs-lookup"><span data-stu-id="f64f0-129">Example</span></span>  
 <span data-ttu-id="f64f0-130">다음 코드 예제에서는 앞의 단계에서 생성한 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f64f0-130">The following code example shows the code from the preceding steps.</span></span>  
  
 [!code-csharp[CodeDOM Class Sample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#1)]
 [!code-vb[CodeDOM Class Sample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#1)]  
  
 <span data-ttu-id="f64f0-131">앞의 예제를 컴파일 및 실행하면 다음 소스 코드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64f0-131">When the preceding example is compiled and executed, it produces the following source code.</span></span>  
  
 [!code-csharp[CodeDOM Class Sample#99](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/SampleCode.cs#99)]
 [!code-vb[CodeDOM Class Sample#99](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/SampleCode.vb#99)]  
  
 <span data-ttu-id="f64f0-132">생성된 소스 코드를 컴파일 및 실행하면 다음 출력이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64f0-132">The generated source code produces the following output when compiled and executed.</span></span>  
  
```output
The object:  
 width = 5.3,  
 height = 6.9,  
 area = 36.57  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f64f0-133">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="f64f0-133">Compiling the Code</span></span>  
  
- <span data-ttu-id="f64f0-134">이 코드 예제를 성공적으로 실행하려면 `FullTrust` 권한이 설정되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f64f0-134">This code example requires the `FullTrust` permission set to execute successfully.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f64f0-135">참조</span><span class="sxs-lookup"><span data-stu-id="f64f0-135">See also</span></span>

- [<span data-ttu-id="f64f0-136">CodeDOM 사용</span><span class="sxs-lookup"><span data-stu-id="f64f0-136">Using the CodeDOM</span></span>](using-the-codedom.md)
- [<span data-ttu-id="f64f0-137">CodeDOM 그래프에서 소스 코드 생성 및 컴파일</span><span class="sxs-lookup"><span data-stu-id="f64f0-137">Generating and Compiling Source Code from a CodeDOM Graph</span></span>](generating-and-compiling-source-code-from-a-codedom-graph.md)
