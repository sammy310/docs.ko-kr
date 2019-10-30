---
title: ICorDebugLoadedModule::GetName 메서드
ms.date: 03/30/2017
ms.assetid: 88c304d5-edaa-4c0e-a8e1-144e8a76877e
ms.openlocfilehash: 4cf2c5c099de3d66878f09ff702a1cad6ddb8f57
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122630"
---
# <a name="icordebugloadedmodulegetname-method"></a><span data-ttu-id="db199-102">ICorDebugLoadedModule::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="db199-102">ICorDebugLoadedModule::GetName Method</span></span>
<span data-ttu-id="db199-103">로드된 모듈의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="db199-103">Gets the name of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db199-104">구문</span><span class="sxs-lookup"><span data-stu-id="db199-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,  
   [out] ULONG32 *pcchName,  
   [out, size_is(cchName),  
   length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db199-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="db199-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="db199-106">[in] `szName` 버퍼의 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="db199-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="db199-107">[out] `szName` 버퍼에 실제로 기록된 문자 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="db199-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="db199-108">[out] 로드된 모듈의 이름을 포함하는 문자 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="db199-108">[out] An array of characters that contain the name of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db199-109">주의</span><span class="sxs-lookup"><span data-stu-id="db199-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="db199-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db199-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db199-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="db199-111">Requirements</span></span>  
 <span data-ttu-id="db199-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="db199-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db199-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db199-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db199-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db199-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db199-115">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db199-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db199-116">참조</span><span class="sxs-lookup"><span data-stu-id="db199-116">See also</span></span>

- [<span data-ttu-id="db199-117">ICorDebugLoadedModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db199-117">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="db199-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db199-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
