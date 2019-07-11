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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e5b387ee7fd4cc0088c90d2b8278fbf18bb36f51
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755688"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="32c95-102">CorSymVarFlag 열거형</span><span class="sxs-lookup"><span data-stu-id="32c95-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="32c95-103">컴파일러에서 생성 된 변수 인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="32c95-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32c95-104">구문</span><span class="sxs-lookup"><span data-stu-id="32c95-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSymVarFlag   
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="32c95-105">멤버</span><span class="sxs-lookup"><span data-stu-id="32c95-105">Members</span></span>  
  
|<span data-ttu-id="32c95-106">멤버</span><span class="sxs-lookup"><span data-stu-id="32c95-106">Member</span></span>|<span data-ttu-id="32c95-107">Description</span><span class="sxs-lookup"><span data-stu-id="32c95-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="32c95-108">컴파일러에서 생성 되는 지정 된 변수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="32c95-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="32c95-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="32c95-109">Requirements</span></span>  
 <span data-ttu-id="32c95-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="32c95-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32c95-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="32c95-111">See also</span></span>

- [<span data-ttu-id="32c95-112">진단 기호 저장소 열거형</span><span class="sxs-lookup"><span data-stu-id="32c95-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
