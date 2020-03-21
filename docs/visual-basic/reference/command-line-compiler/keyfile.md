---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: cffc3c5f0ff3dd48ca2c74bde346a967b209dc5f
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266744"
---
# <a name="-keyfile"></a><span data-ttu-id="d9fa8-102">-keyfile</span><span class="sxs-lookup"><span data-stu-id="d9fa8-102">-keyfile</span></span>
<span data-ttu-id="d9fa8-103">어셈블리에 강력한 이름을 지정하는 키 또는 키 쌍이 포함된 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa8-103">Specifies a file containing a key or key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9fa8-104">구문</span><span class="sxs-lookup"><span data-stu-id="d9fa8-104">Syntax</span></span>  
  
```console
-keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="d9fa8-105">인수</span><span class="sxs-lookup"><span data-stu-id="d9fa8-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="d9fa8-106">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa8-106">Required.</span></span> <span data-ttu-id="d9fa8-107">키가 포함된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa8-107">File that contains the key.</span></span> <span data-ttu-id="d9fa8-108">파일 이름에 공백이 포함된 경우 이름을 따옴표("")로 둘러싸습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa8-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9fa8-109">설명</span><span class="sxs-lookup"><span data-stu-id="d9fa8-109">Remarks</span></span>  
 <span data-ttu-id="d9fa8-110">컴파일러는 공개 키를 어셈블리 매니페스트에 삽입한 다음 개인 키로 최종 어셈블리에 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa8-110">The compiler inserts the public key into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="d9fa8-111">키 파일을 생성하려면 명령줄에 `sn -k file`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa8-111">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="d9fa8-112">자세한 내용은 [Sn.exe(강력한 이름 도구)를](../../../framework/tools/sn-exe-strong-name-tool.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d9fa8-112">For more information, see [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="d9fa8-113">을 사용 `-target:module`하 고 컴파일하는 경우 키 파일의 이름은 모듈에 보관되고 [-addmodule을](../../../visual-basic/reference/command-line-compiler/addmodule.md)사용 하 고 어셈블리를 컴파일할 때 생성 되는 어셈블리에 통합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa8-113">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="d9fa8-114">[-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)를 사용하여 암호화 정보를 컴파일러에 전달할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa8-114">You can also pass your encryption information to the compiler with [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span> <span data-ttu-id="d9fa8-115">부분 서명된 어셈블리가 필요한 경우 [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa8-115">Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="d9fa8-116">Microsoft 중간 언어 모듈의 소스<xref:System.Reflection.AssemblyKeyFileAttribute>코드에서 이 옵션을 사용자 지정 특성()으로 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa8-116">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyFileAttribute>) in the source code for any Microsoft intermediate language module.</span></span>  
  
 <span data-ttu-id="d9fa8-117">동일한 컴파일에서 명령줄 옵션 또는 사용자 지정 특성에 의해 모두 `-keyfile` 및 [-keycontainer가](../../../visual-basic/reference/command-line-compiler/keycontainer.md) 지정되는 경우 컴파일러는 먼저 키 컨테이너를 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa8-117">In case both `-keyfile` and [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) are specified (either by command-line option or by custom attribute) in the same compilation, the compiler first tries the key container.</span></span> <span data-ttu-id="d9fa8-118">키 컨테이너를 찾으면 키 컨테이너의 정보를 사용하여 어셈블리가 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa8-118">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="d9fa8-119">컴파일러에서 키 컨테이너를 찾지 못하면 `-keyfile`로 지정된 파일을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa8-119">If the compiler does not find the key container, it tries the file specified with `-keyfile`.</span></span> <span data-ttu-id="d9fa8-120">이 문제가 성공하면 어셈블리는 키 파일의 정보로 서명되고 키 정보가 키 컨테이너에 `sn -i`설치되므로 다음 컴파일에서 키 컨테이너가 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa8-120">If this succeeds, the assembly is signed with the information in the key file, and the key information is installed in the key container (similar to `sn -i`) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="d9fa8-121">키 파일에는 공개 키만 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa8-121">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="d9fa8-122">어셈블리 서명에 대한 자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용을](../../../standard/assembly/create-use-strong-named.md) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d9fa8-122">See [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d9fa8-123">이 `-keyfile` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다. 명령줄에서 컴파일할 때만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa8-123">The `-keyfile` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="d9fa8-124">예제</span><span class="sxs-lookup"><span data-stu-id="d9fa8-124">Example</span></span>

<span data-ttu-id="d9fa8-125">다음 코드는 소스 `Input.vb` 파일을 컴파일하고 키 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9fa8-125">The following code compiles source file `Input.vb` and specifies a key file.</span></span>

```console
vbc -keyfile:myfile.sn input.vb
```

## <a name="see-also"></a><span data-ttu-id="d9fa8-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9fa8-126">See also</span></span>

- [<span data-ttu-id="d9fa8-127">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="d9fa8-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="d9fa8-128">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="d9fa8-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="d9fa8-129">- 참조 (비주얼 베이직)</span><span class="sxs-lookup"><span data-stu-id="d9fa8-129">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="d9fa8-130">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="d9fa8-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
