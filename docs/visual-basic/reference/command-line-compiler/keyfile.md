---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: 3f476f6b6db1a788002a938eb5ae4bbbed7a5dae
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408577"
---
# <a name="-keyfile"></a><span data-ttu-id="8e250-102">-keyfile</span><span class="sxs-lookup"><span data-stu-id="8e250-102">-keyfile</span></span>
<span data-ttu-id="8e250-103">어셈블리에 강력한 이름을 지정하는 키 또는 키 쌍이 포함된 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e250-103">Specifies a file containing a key or key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e250-104">구문</span><span class="sxs-lookup"><span data-stu-id="8e250-104">Syntax</span></span>  
  
```console
-keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="8e250-105">인수</span><span class="sxs-lookup"><span data-stu-id="8e250-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="8e250-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="8e250-106">Required.</span></span> <span data-ttu-id="8e250-107">키를 포함하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="8e250-107">File that contains the key.</span></span> <span data-ttu-id="8e250-108">파일 이름에 공백이 있으면 이름을 따옴표(" ")로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="8e250-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e250-109">설명</span><span class="sxs-lookup"><span data-stu-id="8e250-109">Remarks</span></span>  
 <span data-ttu-id="8e250-110">컴파일러는 공개 키를 어셈블리 매니페스트에 삽입한 다음, 프라이빗 키를 사용하여 최종 어셈블리에 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="8e250-110">The compiler inserts the public key into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="8e250-111">키 파일을 생성하려면 명령줄에 `sn -k file`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8e250-111">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="8e250-112">자세한 내용은 [Sn.exe(강력한 이름 도구)](../../../framework/tools/sn-exe-strong-name-tool.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e250-112">For more information, see [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="8e250-113">`-target:module`로 컴파일하는 경우 키 파일의 이름이 모듈에 저장되고, [-addmodule](addmodule.md)을 사용하여 어셈블리를 컴파일할 때 생성되는 어셈블리에 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e250-113">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](addmodule.md).</span></span>  
  
 <span data-ttu-id="8e250-114">[-keycontainer](keycontainer.md)를 사용하여 암호화 정보를 컴파일러에 전달할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e250-114">You can also pass your encryption information to the compiler with [-keycontainer](keycontainer.md).</span></span> <span data-ttu-id="8e250-115">부분 서명된 어셈블리가 필요한 경우 [-delaysign](delaysign.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e250-115">Use [-delaysign](delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="8e250-116">Microsoft 중간 언어 모듈의 소스 코드에서 이 옵션을 사용자 지정 특성(<xref:System.Reflection.AssemblyKeyFileAttribute>)으로 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e250-116">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyFileAttribute>) in the source code for any Microsoft intermediate language module.</span></span>  
  
 <span data-ttu-id="8e250-117">동일한 컴파일에서 `-keyfile` 및 [-keycontainer](keycontainer.md)를 명령줄 옵션이나 사용자 지정 특성으로 둘 다 지정하면 컴파일러는 먼저 키 컨테이너를 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e250-117">In case both `-keyfile` and [-keycontainer](keycontainer.md) are specified (either by command-line option or by custom attribute) in the same compilation, the compiler first tries the key container.</span></span> <span data-ttu-id="8e250-118">키 컨테이너를 찾으면 키 컨테이너의 정보를 사용하여 어셈블리가 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e250-118">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="8e250-119">컴파일러는 키 컨테이너를 찾지 못할 경우 `-keyfile`로 지정된 파일을 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e250-119">If the compiler does not find the key container, it tries the file specified with `-keyfile`.</span></span> <span data-ttu-id="8e250-120">해당 파일을 찾으면 키 파일의 정보를 사용하여 어셈블리가 서명되고, 키 정보가 키 컨테이너에 설치되므로(`sn -i`와 유사) 다음에 컴파일할 때 키 컨테이너가 유효해집니다.</span><span class="sxs-lookup"><span data-stu-id="8e250-120">If this succeeds, the assembly is signed with the information in the key file, and the key information is installed in the key container (similar to `sn -i`) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="8e250-121">키 파일에는 공개 키만 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e250-121">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="8e250-122">어셈블리 서명에 대한 자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../../../standard/assembly/create-use-strong-named.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e250-122">See [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8e250-123">Visual Studio 개발 환경 내에서는 `-keyfile` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e250-123">The `-keyfile` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="8e250-124">예제</span><span class="sxs-lookup"><span data-stu-id="8e250-124">Example</span></span>

<span data-ttu-id="8e250-125">다음 코드는 `Input.vb` 소스 파일을 컴파일하고 키 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8e250-125">The following code compiles source file `Input.vb` and specifies a key file.</span></span>

```console
vbc -keyfile:myfile.sn input.vb
```

## <a name="see-also"></a><span data-ttu-id="8e250-126">참조</span><span class="sxs-lookup"><span data-stu-id="8e250-126">See also</span></span>

- [<span data-ttu-id="8e250-127">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="8e250-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="8e250-128">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="8e250-128">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="8e250-129">-reference(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e250-129">-reference (Visual Basic)</span></span>](reference.md)
- [<span data-ttu-id="8e250-130">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="8e250-130">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
