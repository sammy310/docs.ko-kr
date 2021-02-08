---
description: '자세히 알아보기: ICorDebugLoadedModule:: GetBaseAddress 메서드'
title: ICorDebugLoadedModule::GetBaseAddress 메서드
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
ms.openlocfilehash: 2852131d543cfb9593cf4ff607d1f752226c2880
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801269"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="07cc1-103">ICorDebugLoadedModule::GetBaseAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="07cc1-103">ICorDebugLoadedModule::GetBaseAddress Method</span></span>

<span data-ttu-id="07cc1-104">로드된 모듈의 기본 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="07cc1-104">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07cc1-105">구문</span><span class="sxs-lookup"><span data-stu-id="07cc1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07cc1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="07cc1-106">Parameters</span></span>  

 `pAddress`  
 <span data-ttu-id="07cc1-107">[out] 로드된 모듈의 기본 주소에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="07cc1-107">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07cc1-108">설명</span><span class="sxs-lookup"><span data-stu-id="07cc1-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="07cc1-109">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07cc1-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07cc1-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="07cc1-110">Requirements</span></span>  

 <span data-ttu-id="07cc1-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07cc1-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07cc1-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="07cc1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07cc1-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07cc1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07cc1-114">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07cc1-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07cc1-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07cc1-115">See also</span></span>

- [<span data-ttu-id="07cc1-116">ICorDebugLoadedModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="07cc1-116">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="07cc1-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="07cc1-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
