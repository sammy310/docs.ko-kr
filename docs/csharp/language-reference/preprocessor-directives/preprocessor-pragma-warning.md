---
title: '#pragma warning - C# 참조'
ms.date: 07/20/2015
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
ms.openlocfilehash: 5620ea9e5f31c22e26bee95a450335bb179ced25
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712470"
---
# <a name="pragma-warning-c-reference"></a><span data-ttu-id="98da0-102">#pragma warning(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="98da0-102">#pragma warning (C# Reference)</span></span>
<span data-ttu-id="98da0-103">`#pragma warning`은 특정 경고를 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="98da0-103">`#pragma warning` can enable or disable certain warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98da0-104">구문</span><span class="sxs-lookup"><span data-stu-id="98da0-104">Syntax</span></span>  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
## <a name="parameters"></a><span data-ttu-id="98da0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="98da0-105">Parameters</span></span>  
 `warning-list`  
 <span data-ttu-id="98da0-106">경고 번호를 쉼표로 구분한 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="98da0-106">A comma-separated list of warning numbers.</span></span> <span data-ttu-id="98da0-107">"CS" 접두사는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="98da0-107">The "CS" prefix is optional.</span></span>  
  
 <span data-ttu-id="98da0-108">경고 번호를 지정하지 않은 경우 `disable`은 모든 경고를 사용하지 않도록 설정하고 `restore`는 모든 경고를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="98da0-108">When no warning numbers are specified, `disable` disables all warnings and `restore` enables all warnings.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="98da0-109">Visual Studio에서 경고 번호를 찾으려면 프로젝트를 빌드하고 **출력** 창에서 경고 번호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="98da0-109">To find warning numbers in Visual Studio, build your project and then look for the warning numbers in the **Output** window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98da0-110">예제</span><span class="sxs-lookup"><span data-stu-id="98da0-110">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="98da0-111">참조</span><span class="sxs-lookup"><span data-stu-id="98da0-111">See also</span></span>

- [<span data-ttu-id="98da0-112">C# 참조</span><span class="sxs-lookup"><span data-stu-id="98da0-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="98da0-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="98da0-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="98da0-114">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="98da0-114">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="98da0-115">C# 컴파일러 오류</span><span class="sxs-lookup"><span data-stu-id="98da0-115">C# Compiler Errors</span></span>](../compiler-messages/index.md)
