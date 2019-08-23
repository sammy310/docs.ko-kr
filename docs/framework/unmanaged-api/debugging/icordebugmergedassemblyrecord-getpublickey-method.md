---
title: ICorDebugMergedAssemblyRecord::GetPublicKey 메서드
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e08b1edcef3e93caa82be3a4342c6a0264734bea
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940014"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="a5cdf-102">ICorDebugMergedAssemblyRecord::GetPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="a5cdf-102">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>
<span data-ttu-id="a5cdf-103">어셈블리의 공개 키를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a5cdf-103">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5cdf-104">구문</span><span class="sxs-lookup"><span data-stu-id="a5cdf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,   
   [out] ULONG32 *pcbPublicKey,   
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5cdf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a5cdf-105">Parameters</span></span>  
 `cbPublicKey`  
 <span data-ttu-id="a5cdf-106">[in] `pbPublicKey` 배열의 최대 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a5cdf-106">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="a5cdf-107">[out] `pbPublicKey` 배열에 기록된 실제 바이트 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a5cdf-107">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="a5cdf-108">[out] 어셈블리의 공개 키를 포함하는 바이트 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a5cdf-108">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5cdf-109">설명</span><span class="sxs-lookup"><span data-stu-id="a5cdf-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5cdf-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5cdf-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5cdf-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a5cdf-111">Requirements</span></span>  
 <span data-ttu-id="a5cdf-112">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a5cdf-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5cdf-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5cdf-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5cdf-114">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5cdf-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5cdf-115">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5cdf-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5cdf-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="a5cdf-116">See also</span></span>

- [<span data-ttu-id="a5cdf-117">ICorDebugMergedAssemblyRecord 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a5cdf-117">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="a5cdf-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a5cdf-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
