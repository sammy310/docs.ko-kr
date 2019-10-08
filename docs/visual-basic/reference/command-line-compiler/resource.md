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
ms.openlocfilehash: 5bedc346381f6de293933dce14a8c5c3044b246f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005198"
---
# <a name="-resource-visual-basic"></a><span data-ttu-id="7a7c0-102">-리소스 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a7c0-102">-resource (Visual Basic)</span></span>
<span data-ttu-id="7a7c0-103">관리되는 리소스를 어셈블리에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7a7c0-103">Embeds a managed resource in an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a7c0-104">구문</span><span class="sxs-lookup"><span data-stu-id="7a7c0-104">Syntax</span></span>  
  
```console  
-resource:filename[,identifier[,public|private]]  
```

<span data-ttu-id="7a7c0-105">로 구분하거나 여러</span><span class="sxs-lookup"><span data-stu-id="7a7c0-105">or</span></span>  

```console
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="7a7c0-106">인수</span><span class="sxs-lookup"><span data-stu-id="7a7c0-106">Arguments</span></span>  
  
|<span data-ttu-id="7a7c0-107">용어</span><span class="sxs-lookup"><span data-stu-id="7a7c0-107">Term</span></span>|<span data-ttu-id="7a7c0-108">정의</span><span class="sxs-lookup"><span data-stu-id="7a7c0-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="7a7c0-109">필수.</span><span class="sxs-lookup"><span data-stu-id="7a7c0-109">Required.</span></span> <span data-ttu-id="7a7c0-110">출력 파일에 포함할 리소스 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7a7c0-110">The name of the resource file to embed in the output file.</span></span> <span data-ttu-id="7a7c0-111">기본적으로 `filename`은 어셈블리에서 public입니다.</span><span class="sxs-lookup"><span data-stu-id="7a7c0-111">By default, `filename` is public in the assembly.</span></span> <span data-ttu-id="7a7c0-112">공백을 포함 하는 경우 파일 이름을 따옴표 ("")로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="7a7c0-112">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
|`identifier`|<span data-ttu-id="7a7c0-113">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="7a7c0-113">Optional.</span></span> <span data-ttu-id="7a7c0-114">리소스의 논리적 이름입니다. 로드 하는 데 사용 되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7a7c0-114">The logical name for the resource; the name used to load it.</span></span> <span data-ttu-id="7a7c0-115">기본값은 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7a7c0-115">The default is the name of the file.</span></span> <span data-ttu-id="7a7c0-116">필요에 따라 다음을 비롯 하 여 리소스가 어셈블리 매니페스트에서 공용 인지 아니면 개인 인지를 지정할 수 있습니다. `-res:filename.res, myname.res, public`</span><span class="sxs-lookup"><span data-stu-id="7a7c0-116">Optionally, you can specify whether the resource is public or private in the assembly manifest, as with the following: `-res:filename.res, myname.res, public`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a7c0-117">설명</span><span class="sxs-lookup"><span data-stu-id="7a7c0-117">Remarks</span></span>  
 <span data-ttu-id="7a7c0-118">리소스 파일을 출력 파일에 배치 하지 않고 어셈블리에 리소스를 연결 하려면 `-linkresource`을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a7c0-118">Use `-linkresource` to link a resource to an assembly without placing the resource file in the output file.</span></span>  
  
 <span data-ttu-id="7a7c0-119">예를 들어 `filename`이 [resgen.exe (리소스 파일 생성기)](../../../framework/tools/resgen-exe-resource-file-generator.md) 나 개발 환경에서 만든 .NET Framework 리소스 파일인 경우 <xref:System.Resources> 네임 스페이스의 멤버를 사용 하 여 액세스할 수 있습니다 (자세한 내용은 <xref:System.Resources.ResourceManager> 참조).</span><span class="sxs-lookup"><span data-stu-id="7a7c0-119">If `filename` is a .NET Framework resource file created, for example, by the [Resgen.exe (Resource File Generator)](../../../framework/tools/resgen-exe-resource-file-generator.md) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace (see <xref:System.Resources.ResourceManager> for more information).</span></span> <span data-ttu-id="7a7c0-120">런타임에 다른 모든 리소스에 액세스 하려면 <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A> 또는 <xref:System.Reflection.Assembly.GetManifestResourceStream%2A> 메서드 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a7c0-120">To access all other resources at run time, use one of the following methods: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, or <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</span></span>  
  
 <span data-ttu-id="7a7c0-121">`-resource`의 약식은 `-res`입니다.</span><span class="sxs-lookup"><span data-stu-id="7a7c0-121">The short form of `-resource` is `-res`.</span></span>  
  
 <span data-ttu-id="7a7c0-122">Visual Studio IDE에서 `-resource`을 설정 하는 방법에 대 한 자세한 내용은 [응용 프로그램 리소스 관리 (.net)](/visualstudio/ide/managing-application-resources-dotnet)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7a7c0-122">For information about how to set `-resource` in the Visual Studio IDE, see [Managing Application Resources (.NET)](/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a7c0-123">예제</span><span class="sxs-lookup"><span data-stu-id="7a7c0-123">Example</span></span>  
 <span data-ttu-id="7a7c0-124">다음 코드는-0 @no__t 컴파일하고-1 @no__t 리소스 파일을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a7c0-124">The following code compiles `In.vb` and attaches resource file `Rf.resource`.</span></span>  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="7a7c0-125">참조</span><span class="sxs-lookup"><span data-stu-id="7a7c0-125">See also</span></span>

- [<span data-ttu-id="7a7c0-126">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="7a7c0-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="7a7c0-127">-win32resource</span><span class="sxs-lookup"><span data-stu-id="7a7c0-127">-win32resource</span></span>](../../../visual-basic/reference/command-line-compiler/win32resource.md)
- [<span data-ttu-id="7a7c0-128">-linkresource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a7c0-128">-linkresource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/linkresource.md)
- [<span data-ttu-id="7a7c0-129">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a7c0-129">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="7a7c0-130">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="7a7c0-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
