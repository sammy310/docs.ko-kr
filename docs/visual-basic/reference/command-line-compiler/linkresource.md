---
description: '자세한 정보: -linkresource(Visual Basic)'
title: -linkresource
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: 21fc47ecff44230bda0f445bc695706b5ae91eff
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100463704"
---
# <a name="-linkresource-visual-basic"></a><span data-ttu-id="18282-103">-linkresource(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18282-103">-linkresource (Visual Basic)</span></span>

<span data-ttu-id="18282-104">관리되는 리소스에 대한 링크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="18282-104">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18282-105">구문</span><span class="sxs-lookup"><span data-stu-id="18282-105">Syntax</span></span>  
  
```console  
-linkresource:filename[,identifier[,public|private]]  
```

<span data-ttu-id="18282-106">또는</span><span class="sxs-lookup"><span data-stu-id="18282-106">or</span></span>  

```console
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="18282-107">인수</span><span class="sxs-lookup"><span data-stu-id="18282-107">Arguments</span></span>  

 `filename`  
 <span data-ttu-id="18282-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="18282-108">Required.</span></span> <span data-ttu-id="18282-109">어셈블리에 연결할 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="18282-109">The resource file to link to the assembly.</span></span> <span data-ttu-id="18282-110">파일 이름에 공백이 있으면 이름을 따옴표(" ")로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="18282-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="18282-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="18282-111">Optional.</span></span> <span data-ttu-id="18282-112">리소스의 논리적 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="18282-112">The logical name for the resource.</span></span> <span data-ttu-id="18282-113">리소스를 로드하는 데 사용되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="18282-113">The name that is used to load the resource.</span></span> <span data-ttu-id="18282-114">기본값은 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="18282-114">The default is the name of the file.</span></span> <span data-ttu-id="18282-115">필요에 따라 셈블리 매니페스트에서 파일을 퍼블릭 또는 프라이빗으로 지정할 수 있습니다(예: `-linkres:filename.res,myname.res,public`).</span><span class="sxs-lookup"><span data-stu-id="18282-115">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `-linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="18282-116">기본적으로 `filename`은 어셈블리에서 퍼블릭입니다.</span><span class="sxs-lookup"><span data-stu-id="18282-116">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18282-117">설명</span><span class="sxs-lookup"><span data-stu-id="18282-117">Remarks</span></span>  

 <span data-ttu-id="18282-118">`-linkresource` 옵션은 출력 파일에 리소스 파일을 포함하지 않습니다. 이 작업을 수행하려면 `-resource` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="18282-118">The `-linkresource` option does not embed the resource file in the output file; use the `-resource` option to do this.</span></span>  
  
 <span data-ttu-id="18282-119">`-linkresource` 옵션에는 `-target:module` 이외의 `-target` 옵션 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="18282-119">The `-linkresource` option requires one of the `-target` options other than `-target:module`.</span></span>  
  
 <span data-ttu-id="18282-120">예를 들어, `filename`이 [Resgen.exe(리소스 파일 생성기)](../../../framework/tools/resgen-exe-resource-file-generator.md) 또는 개발 환경에서 만들어진 .NET Framework 리소스 파일인 경우 <xref:System.Resources> 네임스페이스의 멤버를 사용하여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18282-120">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="18282-121">(자세한 내용은 <xref:System.Resources.ResourceManager>를 참조하세요.) 런타임 시 다른 모든 리소스에 액세스하려면 <xref:System.Reflection.Assembly> 클래스에서 `GetManifestResource`로 시작하는 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="18282-121">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="18282-122">파일 이름은 모든 파일 형식이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18282-122">The file name can be any file format.</span></span> <span data-ttu-id="18282-123">예를 들어 네이티브 DLL을 어셈블리의 일부로 설정하면 전역 어셈블리 캐시에 설치하고 어셈블리의 관리 코드에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18282-123">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="18282-124">`-linkresource`의 약식은 `-linkres`입니다.</span><span class="sxs-lookup"><span data-stu-id="18282-124">The short form of `-linkresource` is `-linkres`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="18282-125">Visual Studio 개발 환경에서는 `-linkresource` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18282-125">The `-linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18282-126">예제</span><span class="sxs-lookup"><span data-stu-id="18282-126">Example</span></span>  

 <span data-ttu-id="18282-127">다음 코드에서는 `in.vb`를 컴파일하고 리소스 파일 `rf.resource`에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="18282-127">The following code compiles `in.vb` and links to resource file `rf.resource`.</span></span>  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="18282-128">참조</span><span class="sxs-lookup"><span data-stu-id="18282-128">See also</span></span>

- [<span data-ttu-id="18282-129">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="18282-129">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="18282-130">-target(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18282-130">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="18282-131">-resource(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18282-131">-resource (Visual Basic)</span></span>](resource.md)
- [<span data-ttu-id="18282-132">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="18282-132">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
