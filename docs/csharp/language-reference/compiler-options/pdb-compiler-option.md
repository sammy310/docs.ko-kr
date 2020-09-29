---
description: -pdb(C# 컴파일러 옵션)
title: -pdb(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /pdb
helpviewer_keywords:
- -pdb compiler option [C#]
- pdb compiler option [C#]
- /pdb compiler option [C#]
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
ms.openlocfilehash: ced1ee1f4f079830a032a628da96a389ba27da90
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91193857"
---
# <a name="-pdb-c-compiler-options"></a><span data-ttu-id="75c4f-103">-pdb(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="75c4f-103">-pdb (C# Compiler Options)</span></span>

<span data-ttu-id="75c4f-104">**-pdb** 컴파일러 옵션은 디버그 기호 파일의 이름 및 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="75c4f-104">The **-pdb** compiler option specifies the name and location of the debug symbols file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75c4f-105">구문</span><span class="sxs-lookup"><span data-stu-id="75c4f-105">Syntax</span></span>  
  
```console  
-pdb:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="75c4f-106">인수</span><span class="sxs-lookup"><span data-stu-id="75c4f-106">Arguments</span></span>  

 `filename`  
 <span data-ttu-id="75c4f-107">디버그 기호 파일의 이름 및 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="75c4f-107">The name and location of the debug symbols file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75c4f-108">설명</span><span class="sxs-lookup"><span data-stu-id="75c4f-108">Remarks</span></span>  

 <span data-ttu-id="75c4f-109">[-debug(C# 컴파일러 옵션)](./debug-compiler-option.md)를 지정하는 경우 컴파일러는 출력 파일(.exe 또는 .dll)을 만들 디렉터리에 출력 파일의 이름과 동일한 파일 이름으로 .pdb 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="75c4f-109">When you specify [-debug (C# Compiler Options)](./debug-compiler-option.md), the compiler will create a .pdb file in the same directory where the compiler will create the output file (.exe or .dll) with a file name that is the same as the name of the output file.</span></span>  
  
 <span data-ttu-id="75c4f-110">**-pdb**를 사용하면 .pdb 파일에 대해 기본값이 아닌 파일 이름과 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75c4f-110">**-pdb** allows you to specify a non-default file name and location for the .pdb file.</span></span>  
  
 <span data-ttu-id="75c4f-111">Visual Studio 개발 환경에서는 이 컴파일러 옵션을 설정할 수 없으며 프로그래밍 방식으로 변경할 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="75c4f-111">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75c4f-112">예제</span><span class="sxs-lookup"><span data-stu-id="75c4f-112">Example</span></span>  

 <span data-ttu-id="75c4f-113">`t.cs`를 컴파일하고 tt.pdb라는 .pdb 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="75c4f-113">Compile `t.cs` and create a .pdb file called tt.pdb:</span></span>  
  
```console  
csc -debug -pdb:tt t.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="75c4f-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="75c4f-114">See also</span></span>

- [<span data-ttu-id="75c4f-115">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="75c4f-115">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="75c4f-116">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="75c4f-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
