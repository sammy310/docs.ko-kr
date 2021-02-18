---
description: '자세한 정보: -reference(Visual Basic)'
title: -reference
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
ms.openlocfilehash: e84cdf447294a299c26a775327528a94ebba03da
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100474150"
---
# <a name="-reference-visual-basic"></a><span data-ttu-id="47cc9-103">-reference(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47cc9-103">-reference (Visual Basic)</span></span>

<span data-ttu-id="47cc9-104">컴파일러에서 지정된 어셈블리의 형식 정보를 현재 컴파일하고 있는 프로젝트에 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="47cc9-104">Causes the compiler to make type information in the specified assemblies available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47cc9-105">구문</span><span class="sxs-lookup"><span data-stu-id="47cc9-105">Syntax</span></span>  
  
```console  
-reference:fileList  
```

<span data-ttu-id="47cc9-106">또는</span><span class="sxs-lookup"><span data-stu-id="47cc9-106">or</span></span>

```console
-r:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="47cc9-107">인수</span><span class="sxs-lookup"><span data-stu-id="47cc9-107">Arguments</span></span>  
  
|<span data-ttu-id="47cc9-108">용어</span><span class="sxs-lookup"><span data-stu-id="47cc9-108">Term</span></span>|<span data-ttu-id="47cc9-109">정의</span><span class="sxs-lookup"><span data-stu-id="47cc9-109">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="47cc9-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="47cc9-110">Required.</span></span> <span data-ttu-id="47cc9-111">쉼표로 구분된 어셈블리 파일 이름 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="47cc9-111">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="47cc9-112">파일 이름에 공백이 있으면 이름을 따옴표로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="47cc9-112">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47cc9-113">설명</span><span class="sxs-lookup"><span data-stu-id="47cc9-113">Remarks</span></span>  

 <span data-ttu-id="47cc9-114">가져오는 파일에는 어셈블리 메타데이터가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47cc9-114">The file(s) you import must contain assembly metadata.</span></span> <span data-ttu-id="47cc9-115">어셈블리 외부에는 public 형식만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="47cc9-115">Only public types are visible outside the assembly.</span></span> <span data-ttu-id="47cc9-116">[-addmodule](addmodule.md) 옵션은 모듈에서 메타데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="47cc9-116">The [-addmodule](addmodule.md) option imports metadata from a module.</span></span>  
  
 <span data-ttu-id="47cc9-117">다른 어셈블리(어셈블리 B) 자체를 참조하는 어셈블리(어셈블리 A)를 참조하면 다음과 같은 경우 어셈블리 B를 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47cc9-117">If you reference an assembly (Assembly A) which itself references another assembly (Assembly B), you need to reference Assembly B if:</span></span>  
  
- <span data-ttu-id="47cc9-118">어셈블리 A의 형식은 형식에서 상속되거나 어셈블리 B의 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="47cc9-118">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
- <span data-ttu-id="47cc9-119">어셈블리 B의 반환 형식이나 매개 변수 형식을 사용하는 필드, 속성, 이벤트 또는 메서드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="47cc9-119">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="47cc9-120">[-libpath](libpath.md)를 사용하여 하나 이상의 어셈블리 참조가 있는 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="47cc9-120">Use [-libpath](libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="47cc9-121">컴파일러가 모듈이 아닌 어셈블리의 형식을 인식하도록 하려면 강제로 형식을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47cc9-121">For the compiler to recognize a type in an assembly (not a module), it must be forced to resolve the type.</span></span> <span data-ttu-id="47cc9-122">이 작업을 수행하는 방법의 한 예는 형식의 인스턴스를 정의하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="47cc9-122">One example of how you can do this is to define an instance of the type.</span></span> <span data-ttu-id="47cc9-123">컴파일러에 대한 어셈블리의 형식 이름을 확인하는 데 사용할 수 있는 다른 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47cc9-123">Other ways are available to resolve type names in an assembly for the compiler.</span></span> <span data-ttu-id="47cc9-124">예를 들어, 어셈블리의 형식에서 상속되는 경우 형식 이름이 컴파일러에 알려지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47cc9-124">For example, if you inherit from a type in an assembly, the type name then becomes known to the compiler.</span></span>  
  
 <span data-ttu-id="47cc9-125">일반적으로 사용되는 .NET Framework 어셈블리를 참조하는 Vbc.rsp 지시 파일이 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="47cc9-125">The Vbc.rsp response file, which references commonly used .NET Framework assemblies, is used by default.</span></span> <span data-ttu-id="47cc9-126">컴파일러에서 Vbc.rsp를 사용하지 않도록 하려면 `-noconfig`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="47cc9-126">Use `-noconfig` if you do not want the compiler to use Vbc.rsp.</span></span>  
  
 <span data-ttu-id="47cc9-127">`-reference`의 약식은 `-r`입니다.</span><span class="sxs-lookup"><span data-stu-id="47cc9-127">The short form of `-reference` is `-r`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47cc9-128">예제</span><span class="sxs-lookup"><span data-stu-id="47cc9-128">Example</span></span>  

 <span data-ttu-id="47cc9-129">다음 명령은 원본 파일 `Input.vb`와 `Metad1.dll` 및 `Metad2.dll`의 참조 어셈블리를 컴파일하여 `Out.exe`를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="47cc9-129">The following command compiles source file `Input.vb` and reference assemblies from `Metad1.dll` and `Metad2.dll` to produce `Out.exe`.</span></span>  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="47cc9-130">참조</span><span class="sxs-lookup"><span data-stu-id="47cc9-130">See also</span></span>

- [<span data-ttu-id="47cc9-131">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="47cc9-131">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="47cc9-132">-noconfig</span><span class="sxs-lookup"><span data-stu-id="47cc9-132">-noconfig</span></span>](noconfig.md)
- [<span data-ttu-id="47cc9-133">-target(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47cc9-133">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="47cc9-134">공용</span><span class="sxs-lookup"><span data-stu-id="47cc9-134">Public</span></span>](../../language-reference/modifiers/public.md)
- [<span data-ttu-id="47cc9-135">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="47cc9-135">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
