---
title: ICorDebugDataTarget2::GetImageLocation 메서드
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 348c51507006fecfe756cb17fd0d6242617577d7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750226"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a><span data-ttu-id="a10c1-102">ICorDebugDataTarget2::GetImageLocation 메서드</span><span class="sxs-lookup"><span data-stu-id="a10c1-102">ICorDebugDataTarget2::GetImageLocation Method</span></span>
<span data-ttu-id="a10c1-103">모듈의 경로를 모듈의 기준 주소에서 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a10c1-103">Returns the path of a module from the module's base address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a10c1-104">구문</span><span class="sxs-lookup"><span data-stu-id="a10c1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a10c1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a10c1-105">Parameters</span></span>  
 `baseAddress`  
 <span data-ttu-id="a10c1-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) 모듈의 기준 주소를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a10c1-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `cchName`  
 <span data-ttu-id="a10c1-107">[in] 모듈 경로를 수신할 버퍼의 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a10c1-107">[in] The number of characters in the buffer that is to receive the module path.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="a10c1-108">[out] `szName` 버퍼에 기록된 문자 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a10c1-108">[out] A pointer to the number of characters written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="a10c1-109">[out] 모듈의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="a10c1-109">[out] The path of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a10c1-110">설명</span><span class="sxs-lookup"><span data-stu-id="a10c1-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a10c1-111">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a10c1-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a10c1-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a10c1-112">Requirements</span></span>  
 <span data-ttu-id="a10c1-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a10c1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a10c1-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a10c1-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a10c1-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a10c1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a10c1-116">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a10c1-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a10c1-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="a10c1-117">See also</span></span>

- [<span data-ttu-id="a10c1-118">ICorDebugDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a10c1-118">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="a10c1-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a10c1-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
