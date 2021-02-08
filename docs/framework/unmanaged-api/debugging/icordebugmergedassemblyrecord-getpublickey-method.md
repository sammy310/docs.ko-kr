---
description: '자세히 알아보기: ICorDebugMergedAssemblyRecord:: GetPublicKey 메서드'
title: ICorDebugMergedAssemblyRecord::GetPublicKey 메서드
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
ms.openlocfilehash: 15175b0d02773bcbce46bfaec9ce1de3021b7dde
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801100"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="6a1fc-103">ICorDebugMergedAssemblyRecord::GetPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="6a1fc-103">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>

<span data-ttu-id="6a1fc-104">어셈블리의 공개 키를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a1fc-104">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a1fc-105">구문</span><span class="sxs-lookup"><span data-stu-id="6a1fc-105">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,
   [out] ULONG32 *pcbPublicKey,
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a1fc-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6a1fc-106">Parameters</span></span>  

 `cbPublicKey`  
 <span data-ttu-id="6a1fc-107">[in] `pbPublicKey` 배열의 최대 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="6a1fc-107">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="6a1fc-108">[out] `pbPublicKey` 배열에 기록된 실제 바이트 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6a1fc-108">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="6a1fc-109">[out] 어셈블리의 공개 키를 포함하는 바이트 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6a1fc-109">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a1fc-110">설명</span><span class="sxs-lookup"><span data-stu-id="6a1fc-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6a1fc-111">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a1fc-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a1fc-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6a1fc-112">Requirements</span></span>  

 <span data-ttu-id="6a1fc-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6a1fc-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a1fc-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a1fc-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a1fc-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a1fc-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a1fc-116">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a1fc-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a1fc-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a1fc-117">See also</span></span>

- [<span data-ttu-id="6a1fc-118">ICorDebugMergedAssemblyRecord 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a1fc-118">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="6a1fc-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a1fc-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
