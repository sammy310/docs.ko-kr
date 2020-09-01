---
description: -keyfile(C# 컴파일러 옵션)
title: -keyfile(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /keyfile
helpviewer_keywords:
- /keyfile compiler option [C#]
- -keyfile compiler option [C#]
- keyfile compiler option [C#]
ms.assetid: 0815f9de-ace4-4e98-b4c6-13c55dea40c2
ms.openlocfilehash: a97fc00201be1cf8043fc353b20ef447468a06bf
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125490"
---
# <a name="-keyfile-c-compiler-options"></a><span data-ttu-id="ef85d-103">-keyfile(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="ef85d-103">-keyfile (C# Compiler Options)</span></span>
<span data-ttu-id="ef85d-104">암호화 키를 포함하는 파일 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ef85d-104">Specifies the filename containing the cryptographic key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef85d-105">구문</span><span class="sxs-lookup"><span data-stu-id="ef85d-105">Syntax</span></span>  
  
```console  
-keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="ef85d-106">인수</span><span class="sxs-lookup"><span data-stu-id="ef85d-106">Arguments</span></span>  
  
|<span data-ttu-id="ef85d-107">용어</span><span class="sxs-lookup"><span data-stu-id="ef85d-107">Term</span></span>|<span data-ttu-id="ef85d-108">정의</span><span class="sxs-lookup"><span data-stu-id="ef85d-108">Definition</span></span>|  
|----------|----------------|  
|`file`|<span data-ttu-id="ef85d-109">강력한 이름 키를 포함하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ef85d-109">The name of the file containing the strong name key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef85d-110">설명</span><span class="sxs-lookup"><span data-stu-id="ef85d-110">Remarks</span></span>  
 <span data-ttu-id="ef85d-111">이 옵션을 사용하면 컴파일러는 지정된 파일의 퍼블릭 키를 어셈블리 매니페스트에 삽입한 다음 프라이빗 키를 사용하여 최종 어셈블리에 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="ef85d-111">When this option is used, the compiler inserts the public key from the specified file into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="ef85d-112">키 파일을 생성하려면 명령줄에 sn -k `file`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ef85d-112">To generate a key file, type sn -k `file` at the command line.</span></span>  
  
 <span data-ttu-id="ef85d-113">**-target:module**로 컴파일하는 경우 키 파일의 이름이 모듈에 저장되고, [-addmodule](./addmodule-compiler-option.md)을 사용하여 어셈블리를 컴파일할 때 생성되는 어셈블리에 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef85d-113">If you compile with **-target:module**, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](./addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="ef85d-114">[-keycontainer](./keycontainer-compiler-option.md)를 사용하여 암호화 정보를 컴파일러에 전달할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef85d-114">You can also pass your encryption information to the compiler with [-keycontainer](./keycontainer-compiler-option.md).</span></span> <span data-ttu-id="ef85d-115">부분 서명된 어셈블리가 필요한 경우 [-delaysign](./delaysign-compiler-option.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ef85d-115">Use [-delaysign](./delaysign-compiler-option.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="ef85d-116">동일한 컴파일에서 -keyfile 및 -keycontainer를 명령줄 옵션이나 사용자 지정 특성으로 둘 다 지정하면 컴파일러는 먼저 키 컨테이너를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ef85d-116">In case both -keyfile and -keycontainer are specified (either by command line option or by custom attribute) in the same compilation, the compiler will first try the key container.</span></span> <span data-ttu-id="ef85d-117">키 컨테이너를 찾으면 키 컨테이너의 정보를 사용하여 어셈블리가 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef85d-117">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="ef85d-118">컴파일러는 키 컨테이너를 찾지 못할 경우 -keyfile로 지정된 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ef85d-118">If the compiler does not find the key container, it will try the file specified with -keyfile.</span></span> <span data-ttu-id="ef85d-119">해당 파일을 찾으면 키 파일의 정보를 사용하여 어셈블리가 서명되고, 키 정보가 키 컨테이너에 설치되므로(sn -i와 유사) 다음에 컴파일할 때 키 컨테이너가 유효해집니다.</span><span class="sxs-lookup"><span data-stu-id="ef85d-119">If that succeeds, the assembly is signed with the information in the key file and the key information will be installed in the key container (similar to sn -i) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="ef85d-120">키 파일에는 공개 키만 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef85d-120">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="ef85d-121">자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../../../standard/assembly/create-use-strong-named.md) 및 [어셈블리 서명 지연](../../../standard/assembly/delay-sign.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ef85d-121">For more information, see [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) and [Delay Signing an Assembly](../../../standard/assembly/delay-sign.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="ef85d-122">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="ef85d-122">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="ef85d-123">프로젝트의 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ef85d-123">Open the **Properties** page for the project.</span></span>  
  
2. <span data-ttu-id="ef85d-124">**서명** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ef85d-124">Click the **Signing** property page.</span></span>  
  
3. <span data-ttu-id="ef85d-125">**강력한 이름 키 파일 선택** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="ef85d-125">Modify the **Choose a strong name key file** property.</span></span>  
  
 <span data-ttu-id="ef85d-126">프로그래밍 방식으로 <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>을 사용하여 이 컴파일러 옵션에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef85d-126">You can programmatically access this compiler option with <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef85d-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef85d-127">See also</span></span>

- [<span data-ttu-id="ef85d-128">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="ef85d-128">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="ef85d-129">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="ef85d-129">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
