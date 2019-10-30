---
title: 'ICorDebugMergedAssemblyRecord:: GetPublicKey 메서드'
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
ms.openlocfilehash: 9cf5f6b6d12303b3f59588c5fb663c457da79cb9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131392"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="b8e82-102">ICorDebugMergedAssemblyRecord:: GetPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="b8e82-102">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>
<span data-ttu-id="b8e82-103">어셈블리의 공개 키를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b8e82-103">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8e82-104">구문</span><span class="sxs-lookup"><span data-stu-id="b8e82-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,   
   [out] ULONG32 *pcbPublicKey,   
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8e82-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b8e82-105">Parameters</span></span>  
 `cbPublicKey`  
 <span data-ttu-id="b8e82-106">[in] `pbPublicKey` 배열의 최대 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e82-106">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="b8e82-107">[out] `pbPublicKey` 배열에 기록된 실제 바이트 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e82-107">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="b8e82-108">[out] 어셈블리의 공개 키를 포함하는 바이트 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b8e82-108">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8e82-109">주의</span><span class="sxs-lookup"><span data-stu-id="b8e82-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b8e82-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8e82-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8e82-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b8e82-111">Requirements</span></span>  
 <span data-ttu-id="b8e82-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8e82-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8e82-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8e82-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8e82-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8e82-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8e82-115">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8e82-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8e82-116">참조</span><span class="sxs-lookup"><span data-stu-id="b8e82-116">See also</span></span>

- [<span data-ttu-id="b8e82-117">ICorDebugMergedAssemblyRecord 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b8e82-117">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="b8e82-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b8e82-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
