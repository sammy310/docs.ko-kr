---
description: -fullpaths(C# 컴파일러 옵션)
title: -fullpaths(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /fullpaths
helpviewer_keywords:
- /fullpaths compiler option [C#]
- absolute paths [C#]
- fullpaths compiler option [C#]
- full paths [C#]
- -fullpaths compiler option [C#]
ms.assetid: d2a5f857-cbb2-430b-879c-d648aaf0b8c4
ms.openlocfilehash: 1ea1c3ec5e0d981c36044351d02d459386a720fc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173219"
---
# <a name="-fullpaths-c-compiler-options"></a><span data-ttu-id="1de21-103">-fullpaths(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="1de21-103">-fullpaths (C# Compiler Options)</span></span>

<span data-ttu-id="1de21-104">**-fullpaths** 옵션을 사용하면 컴파일러에서는 컴파일 오류 및 경고 목록을 만들때 파일의 전체 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1de21-104">The **-fullpaths** option causes the compiler to specify the full path to the file when listing compilation errors and warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1de21-105">구문</span><span class="sxs-lookup"><span data-stu-id="1de21-105">Syntax</span></span>  
  
```console  
-fullpaths  
```  
  
## <a name="remarks"></a><span data-ttu-id="1de21-106">설명</span><span class="sxs-lookup"><span data-stu-id="1de21-106">Remarks</span></span>  

 <span data-ttu-id="1de21-107">기본적으로 컴파일 도중 발생하는 오류와 경고에서는 오류가 발견된 파일의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1de21-107">By default, errors and warnings that result from compilation specify the name of the file in which an error was found.</span></span> <span data-ttu-id="1de21-108">**-fullpaths** 옵션을 사용하면 컴파일러에서는 파일의 전체 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1de21-108">The **-fullpaths** option causes the compiler to specify the full path to the file.</span></span>  
  
 <span data-ttu-id="1de21-109">이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1de21-109">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1de21-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1de21-110">See also</span></span>

- [<span data-ttu-id="1de21-111">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="1de21-111">C# Compiler Options</span></span>](./index.md)
