---
title: -sdkpath
ms.date: 07/20/2015
f1_keywords:
- sdkpath
- -sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
ms.openlocfilehash: 85aba17b330af1b25b39f462844bc1a4856a448a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403111"
---
# <a name="-sdkpath"></a><span data-ttu-id="6b77b-102">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="6b77b-102">-sdkpath</span></span>
<span data-ttu-id="6b77b-103">mscorlib.dll 및 Microsoft.VisualBasic.dll의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6b77b-103">Specifies the location of mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b77b-104">구문</span><span class="sxs-lookup"><span data-stu-id="6b77b-104">Syntax</span></span>  
  
```console  
-sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="6b77b-105">인수</span><span class="sxs-lookup"><span data-stu-id="6b77b-105">Arguments</span></span>  
 `path`  
 <span data-ttu-id="6b77b-106">컴파일에 사용할 mscorlib.dll 및 Microsoft.VisualBasic.dll 버전을 포함하는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="6b77b-106">The directory containing the versions of mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="6b77b-107">이 경로는 로드될 때까지 확인되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b77b-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="6b77b-108">공백이 있으면 디렉터리 이름을 따옴표(" ")로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="6b77b-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b77b-109">설명</span><span class="sxs-lookup"><span data-stu-id="6b77b-109">Remarks</span></span>  
 <span data-ttu-id="6b77b-110">이 옵션은 Visual Basic 컴파일러가 기본 위치가 아닌 위치에서 mscorlib.dll 및 Microsoft.VisualBasic.dll 파일을 로드하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="6b77b-110">This option tells the Visual Basic compiler to load the mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="6b77b-111">`-sdkpath` 옵션은 [-netcf](netcf.md)와 함께 사용하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6b77b-111">The `-sdkpath` option was designed to be used with [-netcf](netcf.md).</span></span> <span data-ttu-id="6b77b-112">.NET Compact Framework는 이러한 지원 라이브러리의 다른 버전을 사용하여 디바이스에 없는 형식 및 언어 기능을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b77b-112">The .NET Compact Framework uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6b77b-113">Visual Studio 개발 환경 내에서는 `-sdkpath` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b77b-113">The `-sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="6b77b-114">`-sdkpath` 옵션은 Visual Basic 디바이스 프로젝트가 로드될 때 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b77b-114">The `-sdkpath` option is set when a Visual Basic device project is loaded.</span></span>  
  
 <span data-ttu-id="6b77b-115">`-vbruntime` 컴파일러 옵션을 사용하여 컴파일러가 Visual Basic 런타임 라이브러리에 대한 참조 없이 컴파일하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b77b-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `-vbruntime` compiler option.</span></span> <span data-ttu-id="6b77b-116">자세한 내용은 [-vbruntime](vbruntime.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b77b-116">For more information, see [-vbruntime](vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b77b-117">예제</span><span class="sxs-lookup"><span data-stu-id="6b77b-117">Example</span></span>  
 <span data-ttu-id="6b77b-118">다음 코드는 C 드라이브의 .NET Compact Framework 기본 설치 디렉터리에 있는 Mscorlib.dll 및 Microsoft.VisualBasic.dll 버전을 사용하여 .NET Compact Framework로 `Myfile.vb`를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="6b77b-118">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="6b77b-119">일반적으로 최신 버전의 .NET Compact Framework를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6b77b-119">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6b77b-120">참조</span><span class="sxs-lookup"><span data-stu-id="6b77b-120">See also</span></span>

- [<span data-ttu-id="6b77b-121">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="6b77b-121">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="6b77b-122">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="6b77b-122">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="6b77b-123">-netcf</span><span class="sxs-lookup"><span data-stu-id="6b77b-123">-netcf</span></span>](netcf.md)
- [<span data-ttu-id="6b77b-124">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="6b77b-124">-vbruntime</span></span>](vbruntime.md)
