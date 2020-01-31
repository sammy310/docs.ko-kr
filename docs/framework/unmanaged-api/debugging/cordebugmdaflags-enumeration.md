---
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
ms.openlocfilehash: 34a66a8afa118ecaaaeea0b7b78daaadf1da7509
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778270"
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="125ec-102">CorDebugMDAFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="125ec-102">CorDebugMDAFlags Enumeration</span></span>
<span data-ttu-id="125ec-103">MDA(관리 디버깅 도우미)가 실행된 스레드의 상태를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="125ec-103">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="125ec-104">구문</span><span class="sxs-lookup"><span data-stu-id="125ec-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="125ec-105">Members</span><span class="sxs-lookup"><span data-stu-id="125ec-105">Members</span></span>  
  
|<span data-ttu-id="125ec-106">Member</span><span class="sxs-lookup"><span data-stu-id="125ec-106">Member</span></span>|<span data-ttu-id="125ec-107">설명</span><span class="sxs-lookup"><span data-stu-id="125ec-107">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="125ec-108">Mda가 발생 한 스레드가 MDA가 실행 된 후에 누락 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="125ec-108">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="125ec-109">주의</span><span class="sxs-lookup"><span data-stu-id="125ec-109">Remarks</span></span>  
 <span data-ttu-id="125ec-110">호출 스택에서 MDA가 원래 발생 한 위치를 더 이상 설명 하지 않는 경우 스레드는 *지연*된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="125ec-110">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="125ec-111">이는 스레드가 종료 될 때 잘못 된 작업을 실행 하 여 발생 하는 비정상적인 상황입니다.</span><span class="sxs-lookup"><span data-stu-id="125ec-111">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="125ec-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="125ec-112">Requirements</span></span>  
 <span data-ttu-id="125ec-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="125ec-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="125ec-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="125ec-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="125ec-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="125ec-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="125ec-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="125ec-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="125ec-117">참조</span><span class="sxs-lookup"><span data-stu-id="125ec-117">See also</span></span>

- [<span data-ttu-id="125ec-118">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="125ec-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
