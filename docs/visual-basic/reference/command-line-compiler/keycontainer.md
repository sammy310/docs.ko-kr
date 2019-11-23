---
title: -keycontainer
ms.date: 03/10/2018
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
ms.openlocfilehash: be2ad1416e801398fb513593c7f3828e5488bfaf
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005535"
---
# <a name="-keycontainer"></a><span data-ttu-id="1879e-102">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="1879e-102">-keycontainer</span></span>
<span data-ttu-id="1879e-103">어셈블리에 강력한 이름을 지정하는 키 쌍의 키 컨테이너 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1879e-103">Specifies a key container name for a key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1879e-104">구문</span><span class="sxs-lookup"><span data-stu-id="1879e-104">Syntax</span></span>  
  
```console  
-keycontainer:container  
```  
  
## <a name="arguments"></a><span data-ttu-id="1879e-105">인수</span><span class="sxs-lookup"><span data-stu-id="1879e-105">Arguments</span></span>  
  
|<span data-ttu-id="1879e-106">용어</span><span class="sxs-lookup"><span data-stu-id="1879e-106">Term</span></span>|<span data-ttu-id="1879e-107">정의</span><span class="sxs-lookup"><span data-stu-id="1879e-107">Definition</span></span>|  
|---|---|  
|`container`|<span data-ttu-id="1879e-108">필수</span><span class="sxs-lookup"><span data-stu-id="1879e-108">Required.</span></span> <span data-ttu-id="1879e-109">키를 포함 하는 컨테이너 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="1879e-109">Container file that contains the key.</span></span> <span data-ttu-id="1879e-110">이름에 공백이 포함 된 경우 파일 이름을 따옴표 ("")로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="1879e-110">Enclose the file name in quotation marks ("") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1879e-111">주의</span><span class="sxs-lookup"><span data-stu-id="1879e-111">Remarks</span></span>  
 <span data-ttu-id="1879e-112">컴파일러는 공개 키를 어셈블리 매니페스트에 삽입 하 고 최종 어셈블리를 개인 키로 서명 하 여 공유할 구성 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1879e-112">The compiler creates the sharable component by inserting a public key into the assembly manifest and by signing the final assembly with the private key.</span></span> <span data-ttu-id="1879e-113">키 파일을 생성하려면 명령줄에 `sn -k file`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1879e-113">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="1879e-114">`-i` 옵션은 컨테이너에 키 쌍을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="1879e-114">The `-i` option installs the key pair into a container.</span></span> <span data-ttu-id="1879e-115">자세한 내용은 [sn.exe (강력한 이름 도구)](../../../framework/tools/sn-exe-strong-name-tool.md))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1879e-115">For more information, see [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="1879e-116">`-target:module`를 사용 하 여 컴파일하는 경우 키 파일의 이름이 모듈에 저장 되 고 [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)을 사용 하 여 어셈블리를 컴파일할 때 생성 되는 어셈블리에 통합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1879e-116">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="1879e-117">MSIL(Microsoft Intermediate Language) 모듈의 소스 코드에서 이 옵션을 사용자 지정 특성(<xref:System.Reflection.AssemblyKeyNameAttribute>)으로 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1879e-117">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="1879e-118">[-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)을 사용하여 암호화 정보를 컴파일러에 전달할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1879e-118">You can also pass your encryption information to the compiler with [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).</span></span> <span data-ttu-id="1879e-119">부분 서명된 어셈블리가 필요한 경우 [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1879e-119">Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="1879e-120">어셈블리 서명에 대 한 자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../../../standard/assembly/create-use-strong-named.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1879e-120">See [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1879e-121">`-keycontainer` 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1879e-121">The `-keycontainer` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1879e-122">예제</span><span class="sxs-lookup"><span data-stu-id="1879e-122">Example</span></span>  
 <span data-ttu-id="1879e-123">다음 코드는 `Input.vb` 소스 파일을 컴파일하고 키 컨테이너를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1879e-123">The following code compiles source file `Input.vb` and specifies a key container.</span></span>  
  
```console  
vbc -keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="1879e-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1879e-124">See also</span></span>

- [<span data-ttu-id="1879e-125">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="1879e-125">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="1879e-126">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="1879e-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="1879e-127">-keyfile</span><span class="sxs-lookup"><span data-stu-id="1879e-127">-keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [<span data-ttu-id="1879e-128">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="1879e-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
