---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: c13f34c23cad9c909c2c5bd3447f1a8fa53f9b4d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793965"
---
# <a name="-keyfile"></a><span data-ttu-id="6255f-102">-keyfile</span><span class="sxs-lookup"><span data-stu-id="6255f-102">-keyfile</span></span>
<span data-ttu-id="6255f-103">어셈블리에 강력한 이름을 지정하는 키 또는 키 쌍이 포함된 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6255f-103">Specifies a file containing a key or key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6255f-104">구문</span><span class="sxs-lookup"><span data-stu-id="6255f-104">Syntax</span></span>  
  
``` 
-keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="6255f-105">인수</span><span class="sxs-lookup"><span data-stu-id="6255f-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="6255f-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="6255f-106">Required.</span></span> <span data-ttu-id="6255f-107">키가 포함 된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="6255f-107">File that contains the key.</span></span> <span data-ttu-id="6255f-108">파일 이름에 공백이 있으면 이름을 따옴표로 묶습니다 ("").</span><span class="sxs-lookup"><span data-stu-id="6255f-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6255f-109">설명</span><span class="sxs-lookup"><span data-stu-id="6255f-109">Remarks</span></span>  
 <span data-ttu-id="6255f-110">컴파일러는 공개 키를 어셈블리 매니페스트에 삽입 하 고 개인 키를 사용 하 여 최종 어셈블리에 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6255f-110">The compiler inserts the public key into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="6255f-111">키 파일을 생성하려면 명령줄에 `sn -k file`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6255f-111">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="6255f-112">자세한 내용은 [Sn.exe (강력한 이름 도구)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span><span class="sxs-lookup"><span data-stu-id="6255f-112">For more information, see [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="6255f-113">사용 하 여 컴파일하면 `-target:module`를 키 파일의 이름이 모듈에 저장 되 고 사용 하 여 어셈블리를 컴파일할 때 생성 되는 어셈블리에 통합 [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6255f-113">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="6255f-114">[-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)를 사용하여 암호화 정보를 컴파일러에 전달할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6255f-114">You can also pass your encryption information to the compiler with [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span> <span data-ttu-id="6255f-115">부분 서명된 어셈블리가 필요한 경우 [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6255f-115">Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="6255f-116">사용자 지정 특성으로이 옵션을 지정할 수도 있습니다 (<xref:System.Reflection.AssemblyKeyFileAttribute>) 모든 Microsoft intermediate language 모듈에 대 한 소스 코드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6255f-116">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyFileAttribute>) in the source code for any Microsoft intermediate language module.</span></span>  
  
 <span data-ttu-id="6255f-117">경우 둘 다 `-keyfile` 하 고 [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) 에 지정 된 (명령줄 옵션이 나 사용자 지정 특성) 같은 컴파일, 컴파일러는 먼저 키 컨테이너를 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6255f-117">In case both `-keyfile` and [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) are specified (either by command-line option or by custom attribute) in the same compilation, the compiler first tries the key container.</span></span> <span data-ttu-id="6255f-118">키 컨테이너를 찾으면 키 컨테이너의 정보를 사용하여 어셈블리가 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="6255f-118">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="6255f-119">컴파일러는 키 컨테이너를 찾지 못하면 지정 된 파일은 시도 `-keyfile`합니다.</span><span class="sxs-lookup"><span data-stu-id="6255f-119">If the compiler does not find the key container, it tries the file specified with `-keyfile`.</span></span> <span data-ttu-id="6255f-120">이 작업이 성공 하면, 키 파일에서 정보를 사용 하 여 어셈블리가 서명 되 고 키 정보가 키 컨테이너에 설치 됩니다 (비슷합니다 `sn -i`) 다음에 컴파일할 키 컨테이너를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6255f-120">If this succeeds, the assembly is signed with the information in the key file, and the key information is installed in the key container (similar to `sn -i`) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="6255f-121">키 파일에는 공개 키만 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6255f-121">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="6255f-122">참조 [강력한 어셈블리 만들기 및 사용](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) 어셈블리 서명에 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="6255f-122">See [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6255f-123">`-keyfile` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 있는 명령줄에서 컴파일할 경우에 사용할 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6255f-123">The `-keyfile` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6255f-124">예제</span><span class="sxs-lookup"><span data-stu-id="6255f-124">Example</span></span>  
 <span data-ttu-id="6255f-125">다음 코드는 소스 파일 `Input.vb` 키 파일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6255f-125">The following code compiles source file `Input.vb` and specifies a key file.</span></span>  
  
```console  
vbc -keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6255f-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="6255f-126">See also</span></span>

- [<span data-ttu-id="6255f-127">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="6255f-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="6255f-128">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="6255f-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="6255f-129">-참조 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6255f-129">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="6255f-130">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="6255f-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
