---
title: ICorDebugAppDomain2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2
helpviewer_keywords:
- ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type:
- apiref
ms.openlocfilehash: 6f9bcec66ff613d19c1198ac9849ca28c978f537
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788937"
---
# <a name="icordebugappdomain2-interface"></a><span data-ttu-id="ff346-102">ICorDebugAppDomain2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff346-102">ICorDebugAppDomain2 Interface</span></span>

<span data-ttu-id="ff346-103">배열, 포인터, 함수 포인터 및 참조 형식으로 작업 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff346-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="ff346-104">이 인터페이스는 ICorDebugAppDomain 인터페이스의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="ff346-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ff346-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ff346-105">Methods</span></span>  
  
|<span data-ttu-id="ff346-106">메서드</span><span class="sxs-lookup"><span data-stu-id="ff346-106">Method</span></span>|<span data-ttu-id="ff346-107">설명</span><span class="sxs-lookup"><span data-stu-id="ff346-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ff346-108">GetArrayOrPointerType 메서드</span><span class="sxs-lookup"><span data-stu-id="ff346-108">GetArrayOrPointerType Method</span></span>](icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="ff346-109">지정 된 형식의 배열 또는 지정 된 형식에 대 한 포인터 또는 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ff346-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="ff346-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="ff346-110">GetFunctionPointerType</span></span>](icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="ff346-111">지정 된 서명이 있는 함수에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ff346-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff346-112">주의</span><span class="sxs-lookup"><span data-stu-id="ff346-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ff346-113">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff346-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff346-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff346-114">Requirements</span></span>  
 <span data-ttu-id="ff346-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff346-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff346-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ff346-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ff346-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff346-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff346-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff346-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff346-119">참조</span><span class="sxs-lookup"><span data-stu-id="ff346-119">See also</span></span>

- [<span data-ttu-id="ff346-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff346-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
