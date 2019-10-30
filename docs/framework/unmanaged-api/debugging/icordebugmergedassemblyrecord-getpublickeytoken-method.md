---
title: 'ICorDebugMergedAssemblyRecord:: GetPublicKeyToken 메서드'
ms.date: 03/30/2017
ms.assetid: 72020b72-9611-4bc3-b1e7-5a16b023bfa3
ms.openlocfilehash: 95ed1303b33b328d1f14ecea6cc318e14991cd54
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129783"
---
# <a name="icordebugmergedassemblyrecordgetpublickeytoken-method"></a><span data-ttu-id="2cc7e-102">ICorDebugMergedAssemblyRecord:: GetPublicKeyToken 메서드</span><span class="sxs-lookup"><span data-stu-id="2cc7e-102">ICorDebugMergedAssemblyRecord::GetPublicKeyToken Method</span></span>
<span data-ttu-id="2cc7e-103">어셈블리의 공개 키 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2cc7e-103">Gets the assembly's public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cc7e-104">구문</span><span class="sxs-lookup"><span data-stu-id="2cc7e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKeyToken(  
   [in] ULONG32 cbPublicKeyToken,   
   [out] ULONG32 *pcbPublicKeyToken,   
   [out, size_is(cbPublicKeyToken), length_is(*pcbPublicKeyToken)] BYTE pbPublicKeyToken[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2cc7e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2cc7e-105">Parameters</span></span>  
 `cbPublicKeyToken`  
 <span data-ttu-id="2cc7e-106">[in] `pbPublicKeyToken` 배열의 최대 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc7e-106">[in] The maximum number of bytes in the `pbPublicKeyToken` array.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="2cc7e-107">[out] `pbPublicKeyToken` 배열에 기록된 실제 바이트 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc7e-107">[out] A pointer to the actual number of bytes written to the `pbPublicKeyToken` array.</span></span>  
  
 `pbPublicKeyToken`  
 <span data-ttu-id="2cc7e-108">[out] 어셈블리의 공개 키 토큰을 포함하는 바이트 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc7e-108">[out] A pointer to a byte array that contains the assembly's public key token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cc7e-109">주의</span><span class="sxs-lookup"><span data-stu-id="2cc7e-109">Remarks</span></span>  
 <span data-ttu-id="2cc7e-110">어셈블리의 공개 키 토큰은 공개 키에 대한 SHA1 해시의 마지막 8바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc7e-110">An assembly's public key token is the last eight bytes of a SHA1 hash of its public key.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2cc7e-111">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc7e-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cc7e-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2cc7e-112">Requirements</span></span>  
 <span data-ttu-id="2cc7e-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc7e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cc7e-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2cc7e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2cc7e-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2cc7e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cc7e-116">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cc7e-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cc7e-117">참조</span><span class="sxs-lookup"><span data-stu-id="2cc7e-117">See also</span></span>

- [<span data-ttu-id="2cc7e-118">ICorDebugMergedAssemblyRecord 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2cc7e-118">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="2cc7e-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2cc7e-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
