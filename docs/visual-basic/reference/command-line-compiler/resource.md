---
title: -리소스 (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: 2d7da572ecc8d7d20917eaa244eefbcd7abe61f0
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65589515"
---
# <a name="-resource-visual-basic"></a><span data-ttu-id="52ff6-102">-리소스 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52ff6-102">-resource (Visual Basic)</span></span>
<span data-ttu-id="52ff6-103">관리되는 리소스를 어셈블리에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="52ff6-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52ff6-104">구문</span><span class="sxs-lookup"><span data-stu-id="52ff6-104">Syntax</span></span>  
  
```  
-resource:filename[,identifier[,public|private]]  
' -or-  
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="52ff6-105">인수</span><span class="sxs-lookup"><span data-stu-id="52ff6-105">Arguments</span></span>  
  
|<span data-ttu-id="52ff6-106">용어</span><span class="sxs-lookup"><span data-stu-id="52ff6-106">Term</span></span>|<span data-ttu-id="52ff6-107">정의</span><span class="sxs-lookup"><span data-stu-id="52ff6-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="52ff6-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="52ff6-108">Required.</span></span> <span data-ttu-id="52ff6-109">출력 파일에 포함할 리소스 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="52ff6-109">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="52ff6-110">기본적으로 `filename` 어셈블리에 공개 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ff6-110">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="52ff6-111">파일 이름을 따옴표로 묶습니다 ("")에 공백이 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="52ff6-111">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="52ff6-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="52ff6-112">Optional.</span></span> <span data-ttu-id="52ff6-113">리소스에 대 한 논리적 이름 로드 하는 데 사용 하는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="52ff6-113">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="52ff6-114">기본값은 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="52ff6-114">The default is the name of the file.</span></span> <span data-ttu-id="52ff6-115">필요에 따라 다음와 마찬가지로 리소스는 공용 또는 개인 어셈블리 매니페스트에 여부를 지정할 수 있습니다. `-res:filename.res, myname.res, public`</span><span class="sxs-lookup"><span data-stu-id="52ff6-115">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52ff6-116">설명</span><span class="sxs-lookup"><span data-stu-id="52ff6-116">Remarks</span></span>  
 <span data-ttu-id="52ff6-117">사용 하 여 `-linkresource` 출력 파일에 리소스 파일을 배치 하지 않고 어셈블리에 리소스를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ff6-117">Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="52ff6-118">경우 `filename` .NET Framework 리소스 파일이 만들어지면 예를 들어 여는 [Resgen.exe (리소스 파일 생성기)](../../../framework/tools/resgen-exe-resource-file-generator.md) 개발 환경에서의 멤버를 사용 하 여 액세스할 수 있습니다 또는 <xref:System.Resources> 네임 스페이스 (참조 <xref:System.Resources.ResourceManager> 자세한 정보에 대 한).</span><span class="sxs-lookup"><span data-stu-id="52ff6-118">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="52ff6-119">런타임 시 다른 모든 리소스에 액세스 하려면 다음 방법 중 하나를 사용 합니다. <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, 또는 <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="52ff6-119">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="52ff6-120">`-resource`의 약식은 `-res`입니다.</span><span class="sxs-lookup"><span data-stu-id="52ff6-120">The short form of `-resource` is `-res`.</span></span>  
  
 <span data-ttu-id="52ff6-121">설정 하는 방법에 대 한 자세한 `-resource` Visual Studio IDE에서 참조 [응용 프로그램 리소스 관리 (.NET)](/visualstudio/ide/managing-application-resources-dotnet)합니다.</span><span class="sxs-lookup"><span data-stu-id="52ff6-121">For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="52ff6-122">예제</span><span class="sxs-lookup"><span data-stu-id="52ff6-122">Example</span></span>  
 <span data-ttu-id="52ff6-123">다음 코드 컴파일을 `In.vb` 와 연결 합니다. 리소스 파일 `Rf.resource`합니다.</span><span class="sxs-lookup"><span data-stu-id="52ff6-123">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="52ff6-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="52ff6-124">See also</span></span>

- [<span data-ttu-id="52ff6-125">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="52ff6-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="52ff6-126">-win32resource</span><span class="sxs-lookup"><span data-stu-id="52ff6-126">-win32resource</span></span>](../../../visual-basic/reference/command-line-compiler/win32resource.md)
- [<span data-ttu-id="52ff6-127">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52ff6-127">-linkresource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/linkresource.md)
- [<span data-ttu-id="52ff6-128">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52ff6-128">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="52ff6-129">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="52ff6-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
