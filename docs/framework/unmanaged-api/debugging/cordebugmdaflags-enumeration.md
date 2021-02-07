---
description: '자세한 정보: CorDebugMDAFlags 열거'
title: CorDebugMDAFlags 열거형
ms.date: 03/30/2017
api_name:
- CorDebugMDAFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMDAFlags
helpviewer_keywords:
- CorDebugMDAFlags enumeration [.NET Framework debugging]
ms.assetid: 7c0c92fe-8bd2-477f-b307-aca0143732ca
topic_type:
- apiref
ms.openlocfilehash: d7e9178d76286b112035729e997b1f68e2a93fb3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661937"
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="facf4-103">CorDebugMDAFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="facf4-103">CorDebugMDAFlags Enumeration</span></span>

<span data-ttu-id="facf4-104">MDA(관리 디버깅 도우미)가 실행된 스레드의 상태를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="facf4-104">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="facf4-105">구문</span><span class="sxs-lookup"><span data-stu-id="facf4-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="facf4-106">구성원</span><span class="sxs-lookup"><span data-stu-id="facf4-106">Members</span></span>  
  
|<span data-ttu-id="facf4-107">멤버</span><span class="sxs-lookup"><span data-stu-id="facf4-107">Member</span></span>|<span data-ttu-id="facf4-108">설명</span><span class="sxs-lookup"><span data-stu-id="facf4-108">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="facf4-109">Mda가 발생 한 스레드가 MDA가 실행 된 후에 누락 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="facf4-109">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="facf4-110">설명</span><span class="sxs-lookup"><span data-stu-id="facf4-110">Remarks</span></span>  

 <span data-ttu-id="facf4-111">호출 스택에서 MDA가 원래 발생 한 위치를 더 이상 설명 하지 않는 경우 스레드는 *지연* 된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="facf4-111">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="facf4-112">이는 스레드가 종료 될 때 잘못 된 작업을 실행 하 여 발생 하는 비정상적인 상황입니다.</span><span class="sxs-lookup"><span data-stu-id="facf4-112">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="facf4-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="facf4-113">Requirements</span></span>  

 <span data-ttu-id="facf4-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="facf4-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="facf4-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="facf4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="facf4-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="facf4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="facf4-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="facf4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="facf4-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="facf4-118">See also</span></span>

- [<span data-ttu-id="facf4-119">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="facf4-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
