---
description: '#pragma warning - C# 참조'
title: '#pragma warning - C# 참조'
ms.date: 07/20/2015
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
ms.openlocfilehash: 3085c21db386ca215d48bbe8ade83cd26732242c
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137970"
---
# <a name="pragma-warning-c-reference"></a><span data-ttu-id="8c8ca-103">#pragma warning(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="8c8ca-103">#pragma warning (C# Reference)</span></span>
<span data-ttu-id="8c8ca-104">`#pragma warning`은 특정 경고를 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c8ca-104">`#pragma warning` can enable or disable certain warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c8ca-105">구문</span><span class="sxs-lookup"><span data-stu-id="8c8ca-105">Syntax</span></span>  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c8ca-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8c8ca-106">Parameters</span></span>  
 `warning-list`  
 <span data-ttu-id="8c8ca-107">경고 번호를 쉼표로 구분한 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="8c8ca-107">A comma-separated list of warning numbers.</span></span> <span data-ttu-id="8c8ca-108">"CS" 접두사는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8c8ca-108">The "CS" prefix is optional.</span></span>  
  
 <span data-ttu-id="8c8ca-109">경고 번호를 지정하지 않은 경우 `disable`은 모든 경고를 사용하지 않도록 설정하고 `restore`는 모든 경고를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c8ca-109">When no warning numbers are specified, `disable` disables all warnings and `restore` enables all warnings.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8c8ca-110">Visual Studio에서 경고 번호를 찾으려면 프로젝트를 빌드하고 **출력** 창에서 경고 번호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8c8ca-110">To find warning numbers in Visual Studio, build your project and then look for the warning numbers in the **Output** window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c8ca-111">예제</span><span class="sxs-lookup"><span data-stu-id="8c8ca-111">Example</span></span>  
  
```csharp
// pragma_warning.cs  
using System;  
  
#pragma warning disable 414, CS3021  
[CLSCompliant(false)]  
public class C  
{  
    int i = 1;  
    static void Main()  
    {  
    }  
}  
#pragma warning restore CS3021  
[CLSCompliant(false)]  // CS3021  
public class D  
{  
    int i = 1;  
    public static void F()  
    {  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c8ca-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c8ca-112">See also</span></span>

- [<span data-ttu-id="8c8ca-113">C# 참조</span><span class="sxs-lookup"><span data-stu-id="8c8ca-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8c8ca-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="8c8ca-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8c8ca-115">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="8c8ca-115">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="8c8ca-116">C# 컴파일러 오류</span><span class="sxs-lookup"><span data-stu-id="8c8ca-116">C# Compiler Errors</span></span>](../compiler-messages/index.md)
