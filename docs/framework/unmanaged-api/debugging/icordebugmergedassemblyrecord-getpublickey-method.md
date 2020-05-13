---
title: ICorDebugMergedAssemblyRecord::GetPublicKey 메서드
ms.date: 03/30/2017
ms.assetid: 6f4e78ba-082b-489d-8b58-4c35fbcc7a5b
ms.openlocfilehash: 51724aa1ee6101c50c7cdb4b6071fb458814f483
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213545"
---
# <a name="icordebugmergedassemblyrecordgetpublickey-method"></a><span data-ttu-id="cea31-102">ICorDebugMergedAssemblyRecord::GetPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="cea31-102">ICorDebugMergedAssemblyRecord::GetPublicKey Method</span></span>
<span data-ttu-id="cea31-103">어셈블리의 공개 키를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cea31-103">Gets the assembly's public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cea31-104">구문</span><span class="sxs-lookup"><span data-stu-id="cea31-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKey(  
   [in] ULONG32 cbPublicKey,
   [out] ULONG32 *pcbPublicKey,
   [out, size_is(cbPublicKey), length_is(*pcbPublicKey)] BYTE pbPublicKey[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cea31-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cea31-105">Parameters</span></span>  
 `cbPublicKey`  
 <span data-ttu-id="cea31-106">[in] `pbPublicKey` 배열의 최대 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cea31-106">[in] The maximum number of bytes in the `pbPublicKey` array.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="cea31-107">[out] `pbPublicKey` 배열에 기록된 실제 바이트 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cea31-107">[out] A pointer to the actual number of bytes written to the `pbPublicKey` array.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="cea31-108">[out] 어셈블리의 공개 키를 포함하는 바이트 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cea31-108">[out] A pointer to a byte array that contains the assembly's public key.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cea31-109">설명</span><span class="sxs-lookup"><span data-stu-id="cea31-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cea31-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cea31-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cea31-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cea31-111">Requirements</span></span>  
 <span data-ttu-id="cea31-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cea31-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cea31-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cea31-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cea31-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cea31-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cea31-115">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cea31-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cea31-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cea31-116">See also</span></span>

- [<span data-ttu-id="cea31-117">ICorDebugMergedAssemblyRecord 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cea31-117">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="cea31-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cea31-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
