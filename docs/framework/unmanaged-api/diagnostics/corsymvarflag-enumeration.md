---
title: CorSymVarFlag 열거형
ms.date: 03/30/2017
api_name:
- CorSymVarFlag
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymVarFlag
helpviewer_keywords:
- CorSymVarFlag enumeration [.NET Framework debugging]
ms.assetid: c3f7d307-4047-4f9a-be8c-f152fca42fd0
topic_type:
- apiref
ms.openlocfilehash: ed08d9f818f6fc180dbd655243488bf8a527ae11
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725289"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="a93a6-102">CorSymVarFlag 열거형</span><span class="sxs-lookup"><span data-stu-id="a93a6-102">CorSymVarFlag Enumeration</span></span>

<span data-ttu-id="a93a6-103">변수가 컴파일러에서 생성 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a93a6-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a93a6-104">구문</span><span class="sxs-lookup"><span data-stu-id="a93a6-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSymVarFlag
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="a93a6-105">멤버</span><span class="sxs-lookup"><span data-stu-id="a93a6-105">Members</span></span>  
  
|<span data-ttu-id="a93a6-106">멤버</span><span class="sxs-lookup"><span data-stu-id="a93a6-106">Member</span></span>|<span data-ttu-id="a93a6-107">설명</span><span class="sxs-lookup"><span data-stu-id="a93a6-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="a93a6-108">지정 된 변수가 컴파일러에서 생성 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a93a6-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a93a6-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a93a6-109">Requirements</span></span>  

 <span data-ttu-id="a93a6-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="a93a6-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a93a6-111">참조</span><span class="sxs-lookup"><span data-stu-id="a93a6-111">See also</span></span>

- [<span data-ttu-id="a93a6-112">진단 기호 저장소 열거형</span><span class="sxs-lookup"><span data-stu-id="a93a6-112">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
