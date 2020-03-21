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
ms.openlocfilehash: 21e92d8f2fb80c4c41d516ef281bf4fc8a75f4e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176645"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="a54e9-102">CorSymVarFlag 열거형</span><span class="sxs-lookup"><span data-stu-id="a54e9-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="a54e9-103">변수가 컴파일러 생성되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a54e9-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a54e9-104">구문</span><span class="sxs-lookup"><span data-stu-id="a54e9-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSymVarFlag
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="a54e9-105">구성원</span><span class="sxs-lookup"><span data-stu-id="a54e9-105">Members</span></span>  
  
|<span data-ttu-id="a54e9-106">멤버</span><span class="sxs-lookup"><span data-stu-id="a54e9-106">Member</span></span>|<span data-ttu-id="a54e9-107">Description</span><span class="sxs-lookup"><span data-stu-id="a54e9-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="a54e9-108">지정된 변수가 컴파일러에서 생성되는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a54e9-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a54e9-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a54e9-109">Requirements</span></span>  
 <span data-ttu-id="a54e9-110">**헤더:** 코르심.idl, 코르심.h</span><span class="sxs-lookup"><span data-stu-id="a54e9-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a54e9-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a54e9-111">See also</span></span>

- [<span data-ttu-id="a54e9-112">진단 기호 저장소 열거형</span><span class="sxs-lookup"><span data-stu-id="a54e9-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
