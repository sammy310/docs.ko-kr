---
description: '자세히 알아보기: ICorDebugSymbolProvider:: GetTypeProps 메서드'
title: ICorDebugSymbolProvider::GetTypeProps 메서드
ms.date: 03/30/2017
ms.assetid: 35ac4140-91ea-4c77-b1c4-1daf41986ca5
ms.openlocfilehash: b6a4a5a68e1e377fa839940832dfc49574009641
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659662"
---
# <a name="icordebugsymbolprovidergettypeprops-method"></a><span data-ttu-id="f3566-103">ICorDebugSymbolProvider::GetTypeProps 메서드</span><span class="sxs-lookup"><span data-stu-id="f3566-103">ICorDebugSymbolProvider::GetTypeProps Method</span></span>

<span data-ttu-id="f3566-104">vtable에 RVA(상대 가상 주소)가 제공된 경우 해당 제네릭 매개 변수의 서명 수와 같은 형식의 속성 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f3566-104">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3566-105">구문</span><span class="sxs-lookup"><span data-stu-id="f3566-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeProps(  
   [in]  ULONG32 vtableRva,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3566-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f3566-106">Parameters</span></span>  

 `tableRva`  
 <span data-ttu-id="f3566-107">[in] vtable의 RVA(상대 가상 주소)입니다.</span><span class="sxs-lookup"><span data-stu-id="f3566-107">[in] A relative virtual address (RVA) in a vtable.</span></span>  
  
 `cbSignature`  
 <span data-ttu-id="f3566-108">[in] `signature` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f3566-108">[in] The size of the `signature` array.</span></span> <span data-ttu-id="f3566-109">주의 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f3566-109">See the Remarks section.</span></span>  
  
 `pcbSignature`  
 <span data-ttu-id="f3566-110">[out] [out] 반환된 `signature` 배열의 크기에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f3566-110">[out] [out] A pointer to the size of the returned `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="f3566-111">[out] 모든 제네릭 매개 변수의 typespec 서명을 보유하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="f3566-111">[out] A buffer that holds the typespec signatures of all generic parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3566-112">설명</span><span class="sxs-lookup"><span data-stu-id="f3566-112">Remarks</span></span>  

 <span data-ttu-id="f3566-113">형식의 배열에 필요한 크기를 가져오려면 인수를 `signature` 0으로 설정 하 `cbSignature` 고 `signature` 를 **null** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3566-113">To get the required size of the type's `signature` array, set the `cbSignature` argument to 0 and `signature` to **null**.</span></span> <span data-ttu-id="f3566-114">메서드가 반환되면 `signature` 배열에 필요한 바이트 수가 `pcbSignature`에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3566-114">When the method returns, `pcbSignature` will contain the number of bytes required for the `signature` array.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f3566-115">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3566-115">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3566-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f3566-116">Requirements</span></span>  

 <span data-ttu-id="f3566-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3566-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3566-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3566-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3566-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3566-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3566-120">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3566-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3566-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3566-121">See also</span></span>

- [<span data-ttu-id="f3566-122">GetMethodProps 메서드</span><span class="sxs-lookup"><span data-stu-id="f3566-122">GetMethodProps Method</span></span>](icordebugsymbolprovider-getmethodprops-method.md)
- [<span data-ttu-id="f3566-123">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3566-123">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="f3566-124">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f3566-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
