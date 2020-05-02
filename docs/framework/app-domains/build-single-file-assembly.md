---
title: '방법: .NET Framework 단일 파일 어셈블리 빌드'
ms.date: 08/20/2019
helpviewer_keywords:
- assembly manifest, single-file assemblies
- library assemblies
- command-line compilers
- assemblies [.NET Framework], single-file
- output file name for assemblies
- code modules
- single-file assemblies
dev_langs:
- csharp
- vb
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
ms.openlocfilehash: b7cb06da74a21dab6f60f0d4c3ac1748fcbe4526
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81644297"
---
# <a name="how-to-build-a-net-framework-single-file-assembly"></a><span data-ttu-id="7fe45-102">방법: .NET Framework 단일 파일 어셈블리 빌드</span><span class="sxs-lookup"><span data-stu-id="7fe45-102">How to: Build a .NET Framework single-file assembly</span></span>

<span data-ttu-id="7fe45-103">가장 단순한 형식의 어셈블리인 단일 파일 어셈블리에는 형식 정보 및 구현과 [어셈블리 매니페스트](../../standard/assembly/manifest.md)가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fe45-103">A single-file assembly, which is the simplest type of assembly, contains type information and implementation, as well as the [assembly manifest](../../standard/assembly/manifest.md).</span></span> <span data-ttu-id="7fe45-104">명령줄 컴파일러 또는 Visual Studio를 사용하여 .NET Framework를 대상으로 하는 단일 파일 어셈블리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fe45-104">You can use command-line compilers or Visual Studio to create a single-file assembly that targets the .NET Framework.</span></span> <span data-ttu-id="7fe45-105">기본적으로 컴파일러는 확장명이 *.exe*인 어셈블리 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7fe45-105">By default, the compiler creates an assembly file with an *.exe* extension.</span></span>

> [!NOTE]
> <span data-ttu-id="7fe45-106">C# 및 Visual Basic용 Visual Studio는 단일 파일 어셈블리를 만드는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fe45-106">Visual Studio for C# and Visual Basic can be used only to create single-file assemblies.</span></span> <span data-ttu-id="7fe45-107">다중 파일 어셈블리를 만들려면 명령줄 컴파일러나 Visual C++를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe45-107">If you want to create multifile assemblies, you must use command-line compilers or Visual C++.</span></span>

<span data-ttu-id="7fe45-108">다음 절차에는 명령줄 컴파일러를 사용하여 단일 파일 어셈블리를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7fe45-108">The following procedures show how to create single-file assemblies using command-line compilers.</span></span>

## <a name="create-an-assembly-with-an-exe-extension"></a><span data-ttu-id="7fe45-109">확장명이 .exe인 어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="7fe45-109">Create an assembly with an .exe extension</span></span>

<span data-ttu-id="7fe45-110">명령 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe45-110">At the command prompt, type the following command:</span></span>

<span data-ttu-id="7fe45-111">\<*compiler command*> \<*module name*></span><span class="sxs-lookup"><span data-stu-id="7fe45-111">\<*compiler command*> \<*module name*></span></span>

<span data-ttu-id="7fe45-112">이 명령에서 *compiler command*는 코드 모듈에서 사용되는 언어에 대한 컴파일러 명령이고, *module name*은 어셈블리로 컴파일할 코드 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7fe45-112">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span>

<span data-ttu-id="7fe45-113">다음 예제는 `myCode`라는 코드 모듈에서 *myCode.exe*라는 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7fe45-113">The following example creates an assembly named *myCode.exe* from a code module called `myCode`.</span></span>

```csharp
csc myCode.cs
```

```vb
vbc myCode.vb
```

## <a name="create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a><span data-ttu-id="7fe45-114">확장명이 .exe인 어셈블리를 만들고 출력 파일 이름을 지정</span><span class="sxs-lookup"><span data-stu-id="7fe45-114">Create an assembly with an .exe extension and specify the output file name</span></span>

<span data-ttu-id="7fe45-115">명령 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe45-115">At the command prompt, type the following command:</span></span>

<span data-ttu-id="7fe45-116">\<*compiler command*>  **/out:** \<*file name*> \<*module name*></span><span class="sxs-lookup"><span data-stu-id="7fe45-116">\<*compiler command*> **/out:**\<*file name*> \<*module name*></span></span>

<span data-ttu-id="7fe45-117">이 명령에서 *compiler command*는 코드 모듈에서 사용되는 언어에 대한 컴파일러 명령이고, *file name*은 출력 파일 이름이고, *module name*은 어셈블리로 컴파일할 코드 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7fe45-117">In this command, *compiler command* is the compiler command for the language used in your code module, *file name* is the output file name, and *module name* is the name of the code module to compile into the assembly.</span></span>

<span data-ttu-id="7fe45-118">다음 예제는 `myCode`라는 코드 모듈에서 *myAssembly.exe*라는 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7fe45-118">The following example creates an assembly named *myAssembly.exe* from a code module called `myCode`.</span></span>

```csharp
csc -out:myAssembly.exe myCode.cs
```

```vb
vbc -out:myAssembly.exe myCode.vb
```

## <a name="create-library-assemblies"></a><span data-ttu-id="7fe45-119">라이브러리 어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="7fe45-119">Create library assemblies</span></span>
 <span data-ttu-id="7fe45-120">라이브러리 어셈블리는 클래스 라이브러리와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe45-120">A library assembly is similar to a class library.</span></span> <span data-ttu-id="7fe45-121">다른 어셈블리에서 참조되는 형식을 포함하지만 실행을 시작할 진입점이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7fe45-121">It contains types that will be referenced by other assemblies, but it has no entry point to begin execution.</span></span>

<span data-ttu-id="7fe45-122">라이브러리 어셈블리를 만들려면 명령 프롬프트에서 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe45-122">To create a library assembly, at the command prompt, type the following command:</span></span>

<span data-ttu-id="7fe45-123">\<*compiler command*>  **-t:library** \<*module name*></span><span class="sxs-lookup"><span data-stu-id="7fe45-123">\<*compiler command*> **-t:library** \<*module name*></span></span>

<span data-ttu-id="7fe45-124">이 명령에서 *compiler command*는 코드 모듈에서 사용되는 언어에 대한 컴파일러 명령이고, *module name*은 어셈블리로 컴파일할 코드 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7fe45-124">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span> <span data-ttu-id="7fe45-125">**-out:** 옵션 등의 다른 컴파일러 옵션을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fe45-125">You can also use other compiler options, such as the **-out:** option.</span></span>

<span data-ttu-id="7fe45-126">다음 예제는 `myCode`라는 코드 모듈에서 *myCodeAssembly.dll*이라는 라이브러리 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7fe45-126">The following example creates a library assembly named *myCodeAssembly.dll* from a code module called `myCode`.</span></span>

```csharp
csc -out:myCodeLibrary.dll -t:library myCode.cs
```

```vb
vbc -out:myCodeLibrary.dll -t:library myCode.vb
```

## <a name="see-also"></a><span data-ttu-id="7fe45-127">참조</span><span class="sxs-lookup"><span data-stu-id="7fe45-127">See also</span></span>

- [<span data-ttu-id="7fe45-128">어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="7fe45-128">Create assemblies</span></span>](../../standard/assembly/create.md)
- [<span data-ttu-id="7fe45-129">다중 파일 어셈블리</span><span class="sxs-lookup"><span data-stu-id="7fe45-129">Multifile assemblies</span></span>](multifile-assemblies.md)
- [<span data-ttu-id="7fe45-130">방법: 다중 파일 어셈블리 빌드</span><span class="sxs-lookup"><span data-stu-id="7fe45-130">How to: Build a multifile assembly</span></span>](build-multifile-assembly.md)
- [<span data-ttu-id="7fe45-131">어셈블리를 사용한 프로그램</span><span class="sxs-lookup"><span data-stu-id="7fe45-131">Program with assemblies</span></span>](../../standard/assembly/index.md)
