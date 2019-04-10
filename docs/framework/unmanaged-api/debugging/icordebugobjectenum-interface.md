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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0144539987f14bed83bfc9eab2f5ca26d2a609ae
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157774"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="9f1da-102">ICorDebugObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9f1da-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="9f1da-103">ICorDebugEnum 메서드를 구현 하 고 해당 가상 Rva (상대 주소) 하 여 개체의 배열을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f1da-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9f1da-104">메서드</span><span class="sxs-lookup"><span data-stu-id="9f1da-104">Methods</span></span>  
  
|<span data-ttu-id="9f1da-105">메서드</span><span class="sxs-lookup"><span data-stu-id="9f1da-105">Method</span></span>|<span data-ttu-id="9f1da-106">설명</span><span class="sxs-lookup"><span data-stu-id="9f1da-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9f1da-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="9f1da-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-next-method.md)|<span data-ttu-id="9f1da-108">현재 위치부터 시작 하는 열거형에서 지정 된 개수의 개체에 대 한 Rva를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9f1da-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f1da-109">설명</span><span class="sxs-lookup"><span data-stu-id="9f1da-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9f1da-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9f1da-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f1da-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9f1da-111">Requirements</span></span>  
 <span data-ttu-id="9f1da-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9f1da-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f1da-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f1da-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f1da-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f1da-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="9f1da-115">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="9f1da-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9f1da-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="9f1da-116">See also</span></span>

- [<span data-ttu-id="9f1da-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9f1da-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
