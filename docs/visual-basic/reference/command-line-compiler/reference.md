---
title: -reference (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
ms.openlocfilehash: 8f144dbd9376f15ac92e283472dac786a6972045
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775600"
---
# <a name="-reference-visual-basic"></a><span data-ttu-id="f24db-102">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f24db-102">-reference (Visual Basic)</span></span>
<span data-ttu-id="f24db-103">컴파일러가 지정 된 어셈블리의 형식 정보를 현재 컴파일하고 있는 프로젝트에 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f24db-103">Causes the compiler to make type information in the specified assemblies available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f24db-104">구문</span><span class="sxs-lookup"><span data-stu-id="f24db-104">Syntax</span></span>  
  
```console  
-reference:fileList  
```

<span data-ttu-id="f24db-105">or</span><span class="sxs-lookup"><span data-stu-id="f24db-105">or</span></span>

```console
-r:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="f24db-106">인수</span><span class="sxs-lookup"><span data-stu-id="f24db-106">Arguments</span></span>  
  
|<span data-ttu-id="f24db-107">용어</span><span class="sxs-lookup"><span data-stu-id="f24db-107">Term</span></span>|<span data-ttu-id="f24db-108">정의</span><span class="sxs-lookup"><span data-stu-id="f24db-108">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="f24db-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="f24db-109">Required.</span></span> <span data-ttu-id="f24db-110">쉼표로 구분된 어셈블리 파일 이름 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f24db-110">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="f24db-111">파일 이름에 공백이 있으면 이름을 따옴표로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="f24db-111">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f24db-112">주의</span><span class="sxs-lookup"><span data-stu-id="f24db-112">Remarks</span></span>  
 <span data-ttu-id="f24db-113">가져오는 파일에는 어셈블리 메타 데이터가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f24db-113">The file(s) you import must contain assembly metadata.</span></span> <span data-ttu-id="f24db-114">Public 형식만 어셈블리 외부에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f24db-114">Only public types are visible outside the assembly.</span></span> <span data-ttu-id="f24db-115">[-Addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) 옵션은 모듈에서 메타 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f24db-115">The [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) option imports metadata from a module.</span></span>  
  
 <span data-ttu-id="f24db-116">다른 어셈블리 (어셈블리 B)를 참조 하는 어셈블리 (어셈블리 A)를 참조 하는 경우에는 어셈블리 B를 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f24db-116">If you reference an assembly (Assembly A) which itself references another assembly (Assembly B), you need to reference Assembly B if:</span></span>  
  
- <span data-ttu-id="f24db-117">어셈블리 A의 형식은 형식에서 상속되거나 어셈블리 B의 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="f24db-117">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
- <span data-ttu-id="f24db-118">어셈블리 B의 반환 형식이나 매개 변수 형식을 사용하는 필드, 속성, 이벤트 또는 메서드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="f24db-118">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="f24db-119">하나 이상의 어셈블리 참조가 있는 디렉터리를 지정 하려면 [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) 을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f24db-119">Use [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="f24db-120">컴파일러가 모듈이 아니라 어셈블리의 형식을 인식할 수 있도록 하려면 강제로 형식을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f24db-120">For the compiler to recognize a type in an assembly (not a module), it must be forced to resolve the type.</span></span> <span data-ttu-id="f24db-121">이 작업을 수행 하는 방법에 대 한 한 가지 예는 형식의 인스턴스를 정의 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f24db-121">One example of how you can do this is to define an instance of the type.</span></span> <span data-ttu-id="f24db-122">컴파일러에 대 한 어셈블리의 형식 이름을 확인 하는 데 사용할 수 있는 다른 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f24db-122">Other ways are available to resolve type names in an assembly for the compiler.</span></span> <span data-ttu-id="f24db-123">예를 들어, 어셈블리의 형식에서 상속 하는 경우 형식 이름이 컴파일러에 인식 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f24db-123">For example, if you inherit from a type in an assembly, the type name then becomes known to the compiler.</span></span>  
  
 <span data-ttu-id="f24db-124">일반적으로 사용 되는 .NET Framework 어셈블리를 참조 하는 Vbc.exe 지시 파일은 기본적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f24db-124">The Vbc.rsp response file, which references commonly used .NET Framework assemblies, is used by default.</span></span> <span data-ttu-id="f24db-125">컴파일러가 Vbc.rsp를 사용 하지 않도록 하려면 `-noconfig`을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f24db-125">Use `-noconfig` if you do not want the compiler to use Vbc.rsp.</span></span>  
  
 <span data-ttu-id="f24db-126">`-reference`의 약식은 `/r`입니다.</span><span class="sxs-lookup"><span data-stu-id="f24db-126">The short form of `-reference` is `/r`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f24db-127">예제</span><span class="sxs-lookup"><span data-stu-id="f24db-127">Example</span></span>  
 <span data-ttu-id="f24db-128">다음 명령은 `Metad1.dll` 및 `Metad2.dll`에서 소스 파일 `Input.vb` 및 참조 어셈블리를 컴파일하여 `Out.exe`를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f24db-128">The following command compiles source file `Input.vb` and reference assemblies from `Metad1.dll` and `Metad2.dll` to produce `Out.exe`.</span></span>  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f24db-129">참조</span><span class="sxs-lookup"><span data-stu-id="f24db-129">See also</span></span>

- [<span data-ttu-id="f24db-130">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="f24db-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="f24db-131">-noconfig</span><span class="sxs-lookup"><span data-stu-id="f24db-131">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="f24db-132">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f24db-132">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="f24db-133">Public</span><span class="sxs-lookup"><span data-stu-id="f24db-133">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="f24db-134">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="f24db-134">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
