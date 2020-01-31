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
ms.openlocfilehash: 0526c050bcf1316eccf2c756a404fbb971e6d7d0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792736"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="1b181-102">ICorDebugObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1b181-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="1b181-103">ICorDebugEnum 메서드를 구현 하 고 개체의 배열을 Rva (상대 가상 주소)로 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b181-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1b181-104">메서드</span><span class="sxs-lookup"><span data-stu-id="1b181-104">Methods</span></span>  
  
|<span data-ttu-id="1b181-105">메서드</span><span class="sxs-lookup"><span data-stu-id="1b181-105">Method</span></span>|<span data-ttu-id="1b181-106">설명</span><span class="sxs-lookup"><span data-stu-id="1b181-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1b181-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="1b181-107">Next Method</span></span>](icordebugobjectenum-next-method.md)|<span data-ttu-id="1b181-108">현재 위치에서 시작 하 여 열거형에서 지정 된 개체 수의 Rva를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1b181-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b181-109">주의</span><span class="sxs-lookup"><span data-stu-id="1b181-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1b181-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1b181-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b181-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1b181-111">Requirements</span></span>  
 <span data-ttu-id="1b181-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1b181-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b181-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b181-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b181-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b181-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b181-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b181-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b181-116">참조</span><span class="sxs-lookup"><span data-stu-id="1b181-116">See also</span></span>

- [<span data-ttu-id="1b181-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1b181-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
