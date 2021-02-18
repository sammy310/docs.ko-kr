---
description: '자세한 정보: -win32resource'
title: -win32resource
ms.date: 03/13/2018
f1_keywords:
- -win32resource
- win32resource
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
ms.openlocfilehash: a6f14fd2eb1349940c1e208a5baaa4205647f666
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100433486"
---
# <a name="-win32resource"></a><span data-ttu-id="745c3-103">-win32resource</span><span class="sxs-lookup"><span data-stu-id="745c3-103">-win32resource</span></span>

<span data-ttu-id="745c3-104">Win32 리소스 파일을 출력 파일에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="745c3-104">Inserts a Win32 resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="745c3-105">구문</span><span class="sxs-lookup"><span data-stu-id="745c3-105">Syntax</span></span>  
  
```console  
-win32resource:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="745c3-106">인수</span><span class="sxs-lookup"><span data-stu-id="745c3-106">Arguments</span></span>  

 `filename`  
 <span data-ttu-id="745c3-107">출력 파일에 추가할 리소스 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="745c3-107">The name of the resource file to add to your output file.</span></span> <span data-ttu-id="745c3-108">공백이 있으면 파일 이름을 따옴표(" ")로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="745c3-108">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="745c3-109">설명</span><span class="sxs-lookup"><span data-stu-id="745c3-109">Remarks</span></span>  

 <span data-ttu-id="745c3-110">Microsoft Windows RC(리소스 컴파일러)를 사용하여 Win32 리소스 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="745c3-110">You can create a Win32 resource file with the Microsoft Windows Resource Compiler (RC).</span></span>  
  
 <span data-ttu-id="745c3-111">Win32 리소스는 **파일 탐색기** 에서 애플리케이션을 식별하는 데 도움이 되는 버전 정보나 비트맵(아이콘) 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="745c3-111">A Win32 resource can contain version or bitmap (icon) information that helps identify your application in **File Explorer**.</span></span> <span data-ttu-id="745c3-112">`-win32resource`를 지정하지 않으면 컴파일러에서 어셈블리 버전을 기반으로 버전 정보를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="745c3-112">If you do not specify `-win32resource`, the compiler generates version information based on the assembly version.</span></span> <span data-ttu-id="745c3-113">`-win32resource` 및 `-win32icon` 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="745c3-113">The `-win32resource` and `-win32icon` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="745c3-114">.NET Framework 리소스 파일 또는 [-resource (Visual Basic)](resource.md)를 참조하여 .NET Framework 리소스 파일을 연결하려면 [-linkresource(Visual Basic)](linkresource.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="745c3-114">See [-linkresource (Visual Basic)](linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](resource.md) to attach a .NET Framework resource file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="745c3-115">Visual Studio 개발 환경 내에서는 `-win32resource` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="745c3-115">The `-win32resource` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="745c3-116">예제</span><span class="sxs-lookup"><span data-stu-id="745c3-116">Example</span></span>  

 <span data-ttu-id="745c3-117">다음 코드에서는 `In.vb`를 컴파일하고 Win32 리소스 파일 `Rf.res`를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="745c3-117">The following code compiles `In.vb` and attaches a Win32 resource file, `Rf.res`:</span></span>  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="745c3-118">참조</span><span class="sxs-lookup"><span data-stu-id="745c3-118">See also</span></span>

- [<span data-ttu-id="745c3-119">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="745c3-119">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="745c3-120">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="745c3-120">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
