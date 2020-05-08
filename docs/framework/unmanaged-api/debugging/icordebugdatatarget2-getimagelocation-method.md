---
title: ICorDebugDataTarget2::GetImageLocation 메서드
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
ms.openlocfilehash: 185b6a4979491a323f6eb15ab08a06f87fabc8d3
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976462"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a><span data-ttu-id="4e38f-102">ICorDebugDataTarget2::GetImageLocation 메서드</span><span class="sxs-lookup"><span data-stu-id="4e38f-102">ICorDebugDataTarget2::GetImageLocation Method</span></span>
<span data-ttu-id="4e38f-103">모듈의 경로를 모듈의 기준 주소에서 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4e38f-103">Returns the path of a module from the module's base address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e38f-104">구문</span><span class="sxs-lookup"><span data-stu-id="4e38f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e38f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4e38f-105">Parameters</span></span>  
 `baseAddress`  
 <span data-ttu-id="4e38f-106">진행 모듈의 기준 주소를 나타내는 [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4e38f-106">[in] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `cchName`  
 <span data-ttu-id="4e38f-107">[in] 모듈 경로를 수신할 버퍼의 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4e38f-107">[in] The number of characters in the buffer that is to receive the module path.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="4e38f-108">[out] `szName` 버퍼에 기록된 문자 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4e38f-108">[out] A pointer to the number of characters written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="4e38f-109">[out] 모듈의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="4e38f-109">[out] The path of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e38f-110">설명</span><span class="sxs-lookup"><span data-stu-id="4e38f-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4e38f-111">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e38f-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e38f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4e38f-112">Requirements</span></span>  
 <span data-ttu-id="4e38f-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e38f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e38f-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e38f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e38f-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e38f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e38f-116">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e38f-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e38f-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e38f-117">See also</span></span>

- [<span data-ttu-id="4e38f-118">ICorDebugDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e38f-118">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="4e38f-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e38f-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
