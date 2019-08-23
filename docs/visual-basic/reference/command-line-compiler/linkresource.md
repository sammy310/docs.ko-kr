---
title: -linkresource (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: d92b0d08daf660880b648875c67c3b78069143d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69924851"
---
# <a name="-linkresource-visual-basic"></a><span data-ttu-id="a08f9-102">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a08f9-102">-linkresource (Visual Basic)</span></span>
<span data-ttu-id="a08f9-103">관리되는 리소스에 대한 링크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a08f9-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a08f9-104">구문</span><span class="sxs-lookup"><span data-stu-id="a08f9-104">Syntax</span></span>  
  
```  
-linkresource:filename[,identifier[,public|private]]  
' -or-  
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="a08f9-105">인수</span><span class="sxs-lookup"><span data-stu-id="a08f9-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="a08f9-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a08f9-106">Required.</span></span> <span data-ttu-id="a08f9-107">어셈블리에 연결할 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="a08f9-107">The resource file to link to the assembly.</span></span> <span data-ttu-id="a08f9-108">파일 이름에 공백이 포함 된 경우 이름을 큰따옴표 ("")로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="a08f9-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="a08f9-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a08f9-109">Optional.</span></span> <span data-ttu-id="a08f9-110">리소스의 논리적 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a08f9-110">The logical name for the resource.</span></span> <span data-ttu-id="a08f9-111">리소스를 로드 하는 데 사용 되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a08f9-111">The name that is used to load the resource.</span></span> <span data-ttu-id="a08f9-112">기본값은 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a08f9-112">The default is the name of the file.</span></span> <span data-ttu-id="a08f9-113">필요에 따라 어셈블리 매니페스트에서 파일이 공개 인지 아니면 개인 파일 인지를 지정할 수 있습니다 (예: `-linkres:filename.res,myname.res,public`).</span><span class="sxs-lookup"><span data-stu-id="a08f9-113">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `-linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="a08f9-114">기본적 `filename` 으로는 어셈블리에서 public입니다.</span><span class="sxs-lookup"><span data-stu-id="a08f9-114">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a08f9-115">설명</span><span class="sxs-lookup"><span data-stu-id="a08f9-115">Remarks</span></span>  
 <span data-ttu-id="a08f9-116">옵션은 출력 파일에 리소스 파일을 포함 하지 않습니다. `-resource` 옵션을 사용 하 여이 작업을 수행 합니다. `-linkresource`</span><span class="sxs-lookup"><span data-stu-id="a08f9-116">The `-linkresource` option does not embed the resource file in the output file; use the `-resource` option to do this.</span></span>  
  
 <span data-ttu-id="a08f9-117">옵션 `-linkresource` 에는 이외의 `-target` `-target:module`옵션 중 하나가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a08f9-117">The `-linkresource` option requires one of the `-target` options other than `-target:module`.</span></span>  
  
 <span data-ttu-id="a08f9-118">예 `filename` 를 들어,를 [resgen.exe (리소스 파일 생성기)](../../../framework/tools/resgen-exe-resource-file-generator.md) 나 개발 환경에서 만든 .NET Framework 리소스 파일인 경우에는 <xref:System.Resources> 네임 스페이스의 멤버를 사용 하 여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a08f9-118">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="a08f9-119">자세한 내용은 <xref:System.Resources.ResourceManager>을 참조하세요. 런타임에 다른 모든 리소스에 액세스 하려면 `GetManifestResource` <xref:System.Reflection.Assembly> 클래스에서로 시작 하는 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a08f9-119">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="a08f9-120">파일 이름은 임의의 파일 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a08f9-120">The file name can be any file format.</span></span> <span data-ttu-id="a08f9-121">예를 들어 네이티브 DLL을 어셈블리의 일부로 설정하면 전역 어셈블리 캐시에 설치하고 어셈블리의 관리 코드에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a08f9-121">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="a08f9-122">`-linkresource`의 약식은 `-linkres`입니다.</span><span class="sxs-lookup"><span data-stu-id="a08f9-122">The short form of `-linkresource` is `-linkres`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a08f9-123">이 `-linkresource` 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a08f9-123">The `-linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a08f9-124">예제</span><span class="sxs-lookup"><span data-stu-id="a08f9-124">Example</span></span>  
 <span data-ttu-id="a08f9-125">다음 코드는를 `in.vb` 컴파일하고 리소스 파일 `rf.resource`에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="a08f9-125">The following code compiles `in.vb` and links to resource file `rf.resource`.</span></span>  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="a08f9-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="a08f9-126">See also</span></span>

- [<span data-ttu-id="a08f9-127">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="a08f9-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="a08f9-128">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a08f9-128">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="a08f9-129">-리소스 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a08f9-129">-resource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/resource.md)
- [<span data-ttu-id="a08f9-130">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="a08f9-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
