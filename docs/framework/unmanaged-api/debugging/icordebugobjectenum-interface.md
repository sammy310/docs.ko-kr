---
title: ICorDebugObjectEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum
helpviewer_keywords:
- ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type:
- apiref
ms.openlocfilehash: 9400c4fa3ddcefef923d7bcfaae80e2cef62dc7d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695467"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="eb014-102">ICorDebugObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eb014-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="eb014-103">ICorDebugEnum 메서드를 구현 하 고 개체의 배열을 Rva (상대 가상 주소)로 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb014-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eb014-104">메서드</span><span class="sxs-lookup"><span data-stu-id="eb014-104">Methods</span></span>  
  
|<span data-ttu-id="eb014-105">메서드</span><span class="sxs-lookup"><span data-stu-id="eb014-105">Method</span></span>|<span data-ttu-id="eb014-106">설명</span><span class="sxs-lookup"><span data-stu-id="eb014-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eb014-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="eb014-107">Next Method</span></span>](icordebugobjectenum-next-method.md)|<span data-ttu-id="eb014-108">현재 위치에서 시작 하 여 열거형에서 지정 된 개체 수의 Rva를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eb014-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb014-109">설명</span><span class="sxs-lookup"><span data-stu-id="eb014-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eb014-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb014-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb014-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eb014-111">Requirements</span></span>  

 <span data-ttu-id="eb014-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eb014-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb014-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb014-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb014-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb014-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb014-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb014-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb014-116">참조</span><span class="sxs-lookup"><span data-stu-id="eb014-116">See also</span></span>

- [<span data-ttu-id="eb014-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eb014-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
