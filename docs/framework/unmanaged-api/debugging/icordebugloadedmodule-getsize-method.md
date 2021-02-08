---
description: '자세히 알아보기: ICorDebugLoadedModule:: GetSize 메서드'
title: ICorDebugLoadedModule::GetSize 메서드
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
ms.openlocfilehash: 6701d2578559a039f352df19bf9e859658c6687f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801243"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="4b909-103">ICorDebugLoadedModule::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="4b909-103">ICorDebugLoadedModule::GetSize Method</span></span>

<span data-ttu-id="4b909-104">로드된 모듈의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4b909-104">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b909-105">구문</span><span class="sxs-lookup"><span data-stu-id="4b909-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b909-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4b909-106">Parameters</span></span>  

 `pcBytes`  
 <span data-ttu-id="4b909-107">[out] 로드된 모듈의 바이트 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4b909-107">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b909-108">설명</span><span class="sxs-lookup"><span data-stu-id="4b909-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4b909-109">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b909-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b909-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4b909-110">Requirements</span></span>  

 <span data-ttu-id="4b909-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4b909-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b909-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b909-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b909-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b909-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b909-114">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b909-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b909-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b909-115">See also</span></span>

- [<span data-ttu-id="4b909-116">ICorDebugLoadedModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b909-116">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="4b909-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b909-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
