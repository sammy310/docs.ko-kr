---
description: '다음에 대 한 자세한 정보: CorSymVarFlag 열거형'
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
ms.openlocfilehash: 28f4b4775e20703e5dcaa7daf69affd3548aa3f2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800463"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="4f5bb-103">CorSymVarFlag 열거형</span><span class="sxs-lookup"><span data-stu-id="4f5bb-103">CorSymVarFlag Enumeration</span></span>

<span data-ttu-id="4f5bb-104">변수가 컴파일러에서 생성 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4f5bb-104">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f5bb-105">구문</span><span class="sxs-lookup"><span data-stu-id="4f5bb-105">Syntax</span></span>  
  
```cpp  
typedef enum CorSymVarFlag
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="4f5bb-106">구성원</span><span class="sxs-lookup"><span data-stu-id="4f5bb-106">Members</span></span>  
  
|<span data-ttu-id="4f5bb-107">멤버</span><span class="sxs-lookup"><span data-stu-id="4f5bb-107">Member</span></span>|<span data-ttu-id="4f5bb-108">설명</span><span class="sxs-lookup"><span data-stu-id="4f5bb-108">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="4f5bb-109">지정 된 변수가 컴파일러에서 생성 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4f5bb-109">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4f5bb-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4f5bb-110">Requirements</span></span>  

 <span data-ttu-id="4f5bb-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="4f5bb-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f5bb-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f5bb-112">See also</span></span>

- [<span data-ttu-id="4f5bb-113">진단 기호 저장소 열거형</span><span class="sxs-lookup"><span data-stu-id="4f5bb-113">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
