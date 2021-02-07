---
description: '자세히 알아보기: ICorDebugTypeEnum 인터페이스'
title: ICorDebugTypeEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugTypeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugTypeEnum
helpviewer_keywords:
- ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: 159ccfcf-b37c-4ad9-8e0d-a9a443262472
topic_type:
- apiref
ms.openlocfilehash: c0bf5c6a67b13b2fe29cb3551e287b2597a01aea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690732"
---
# <a name="icordebugtypeenum-interface"></a><span data-ttu-id="ade2f-103">ICorDebugTypeEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ade2f-103">ICorDebugTypeEnum Interface</span></span>

<span data-ttu-id="ade2f-104">"ICorDebugEnum" 메서드를 구현 하 고 "ICorDebugType" 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade2f-104">Implements "ICorDebugEnum" methods and enumerates "ICorDebugType" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ade2f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ade2f-105">Methods</span></span>  
  
|<span data-ttu-id="ade2f-106">메서드</span><span class="sxs-lookup"><span data-stu-id="ade2f-106">Method</span></span>|<span data-ttu-id="ade2f-107">설명</span><span class="sxs-lookup"><span data-stu-id="ade2f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ade2f-108">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="ade2f-108">Next Method</span></span>](icordebugtypeenum-next-method.md)|<span data-ttu-id="ade2f-109">`ICorDebugType`현재 위치에서 시작 하 여 열거형에서 지정 된 수의 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ade2f-109">Gets the specified number of `ICorDebugType` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ade2f-110">설명</span><span class="sxs-lookup"><span data-stu-id="ade2f-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ade2f-111">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ade2f-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ade2f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ade2f-112">Requirements</span></span>  

 <span data-ttu-id="ade2f-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ade2f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ade2f-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ade2f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ade2f-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ade2f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ade2f-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ade2f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ade2f-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ade2f-117">See also</span></span>

- [<span data-ttu-id="ade2f-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ade2f-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
