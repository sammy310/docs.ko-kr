---
title: ICorDebugMergedAssemblyRecord::GetPublicKeyToken 메서드
ms.date: 03/30/2017
ms.assetid: 72020b72-9611-4bc3-b1e7-5a16b023bfa3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 626aa53740839df0b47a876b3e82814a63ffd82d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936860"
---
# <a name="icordebugmergedassemblyrecordgetpublickeytoken-method"></a><span data-ttu-id="11456-102">ICorDebugMergedAssemblyRecord::GetPublicKeyToken 메서드</span><span class="sxs-lookup"><span data-stu-id="11456-102">ICorDebugMergedAssemblyRecord::GetPublicKeyToken Method</span></span>
<span data-ttu-id="11456-103">어셈블리의 공개 키 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="11456-103">Gets the assembly's public key token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11456-104">구문</span><span class="sxs-lookup"><span data-stu-id="11456-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKeyToken(  
   [in] ULONG32 cbPublicKeyToken,   
   [out] ULONG32 *pcbPublicKeyToken,   
   [out, size_is(cbPublicKeyToken), length_is(*pcbPublicKeyToken)] BYTE pbPublicKeyToken[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11456-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="11456-105">Parameters</span></span>  
 `cbPublicKeyToken`  
 <span data-ttu-id="11456-106">[in] `pbPublicKeyToken` 배열의 최대 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="11456-106">[in] The maximum number of bytes in the `pbPublicKeyToken` array.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="11456-107">[out] `pbPublicKeyToken` 배열에 기록된 실제 바이트 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="11456-107">[out] A pointer to the actual number of bytes written to the `pbPublicKeyToken` array.</span></span>  
  
 `pbPublicKeyToken`  
 <span data-ttu-id="11456-108">[out] 어셈블리의 공개 키 토큰을 포함하는 바이트 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="11456-108">[out] A pointer to a byte array that contains the assembly's public key token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11456-109">설명</span><span class="sxs-lookup"><span data-stu-id="11456-109">Remarks</span></span>  
 <span data-ttu-id="11456-110">어셈블리의 공개 키 토큰은 공개 키에 대한 SHA1 해시의 마지막 8바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="11456-110">An assembly's public key token is the last eight bytes of a SHA1 hash of its public key.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="11456-111">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11456-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11456-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="11456-112">Requirements</span></span>  
 <span data-ttu-id="11456-113">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="11456-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11456-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11456-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11456-115">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11456-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11456-116">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11456-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11456-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="11456-117">See also</span></span>

- [<span data-ttu-id="11456-118">ICorDebugMergedAssemblyRecord 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11456-118">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="11456-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11456-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
