---
title: ICorDebugLoadedModule::GetName 메서드
ms.date: 03/30/2017
ms.assetid: 88c304d5-edaa-4c0e-a8e1-144e8a76877e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9bf09c01d24315c3f239911326f1844a0b2cc101
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111269"
---
# <a name="icordebugloadedmodulegetname-method"></a><span data-ttu-id="113ee-102">ICorDebugLoadedModule::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="113ee-102">ICorDebugLoadedModule::GetName Method</span></span>
<span data-ttu-id="113ee-103">로드된 모듈의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="113ee-103">Gets the name of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="113ee-104">구문</span><span class="sxs-lookup"><span data-stu-id="113ee-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,  
   [out] ULONG32 *pcchName,  
   [out, size_is(cchName),  
   length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="113ee-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="113ee-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="113ee-106">[in] `szName` 버퍼의 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="113ee-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="113ee-107">[out] `szName` 버퍼에 실제로 기록된 문자 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="113ee-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="113ee-108">[out] 로드된 모듈의 이름을 포함하는 문자 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="113ee-108">[out] An array of characters that contain the name of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="113ee-109">설명</span><span class="sxs-lookup"><span data-stu-id="113ee-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="113ee-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="113ee-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="113ee-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="113ee-111">Requirements</span></span>  
 <span data-ttu-id="113ee-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="113ee-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="113ee-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="113ee-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="113ee-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="113ee-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="113ee-115">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="113ee-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="113ee-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="113ee-116">See also</span></span>

- [<span data-ttu-id="113ee-117">ICorDebugLoadedModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="113ee-117">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="113ee-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="113ee-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
