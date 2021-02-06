---
description: '자세히 알아보기: ICorDebugSymbolProvider:: GetMethodProps 메서드'
title: ICorDebugSymbolProvider::GetMethodProps 메서드
ms.date: 03/30/2017
ms.assetid: 8f836b80-b7a5-460b-bf76-5f0e45652aea
ms.openlocfilehash: 53a329426ecadfe5559c0e6a08ffbd250163e177
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659727"
---
# <a name="icordebugsymbolprovidergetmethodprops-method"></a><span data-ttu-id="59e84-103">ICorDebugSymbolProvider::GetMethodProps 메서드</span><span class="sxs-lookup"><span data-stu-id="59e84-103">ICorDebugSymbolProvider::GetMethodProps Method</span></span>

<span data-ttu-id="59e84-104">해당 메서드에 RVA(상대 가상 주소)가 제공된 경우 메서드의 메타데이터 토큰 및 제네릭 매개 변수 정보와 같은 메서드 속성 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="59e84-104">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59e84-105">구문</span><span class="sxs-lookup"><span data-stu-id="59e84-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodProps(  
   [in]  ULONG32 codeRva,  
   [out] mdToken *pMethodToken,  
   [out] ULONG32 *pcGenericParams,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59e84-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="59e84-106">Parameters</span></span>  

 `codeRVA`  
 <span data-ttu-id="59e84-107">[in] 정보를 검색할 메서드의 상대 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="59e84-107">[in] A relative virtual address in the method about which information is to be retrieved.</span></span>  
  
 `pMethodToken`  
 <span data-ttu-id="59e84-108">[out] 메서드의 메타데이터 토큰에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="59e84-108">[out] A pointer to the method's metadata token.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="59e84-109">[out] 이 메서드와 연결된 제네릭 매개 변수 개수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="59e84-109">[out] A pointer to the number of generic parameters associated with this method.</span></span>  
  
 `cbSignature`  
 <span data-ttu-id="59e84-110">[in] `signature` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="59e84-110">[in] The size of the `signature` array.</span></span> <span data-ttu-id="59e84-111">주의 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="59e84-111">See the Remarks section.</span></span>  
  
 `pcbSignature`  
 <span data-ttu-id="59e84-112">[out] 반환된 `signature` 배열의 크기에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="59e84-112">[out] A pointer to the size of the returned `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="59e84-113">[out] 모든 제네릭 매개 변수의 typespec 서명을 보유하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="59e84-113">[out] A buffer that holds the typespec signatures of all generic parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59e84-114">설명</span><span class="sxs-lookup"><span data-stu-id="59e84-114">Remarks</span></span>  

 <span data-ttu-id="59e84-115">메서드의 배열에 필요한 크기를 가져오려면 인수를 `signature` 0으로 설정 하 `cbSignature` 고 `signature` 를 **null** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="59e84-115">To get the required size of the method's `signature` array, set the `cbSignature` argument to 0 and `signature` to **null**.</span></span> <span data-ttu-id="59e84-116">메서드가 반환되면 `signature` 배열에 필요한 바이트 수가 `pcbSignature`에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="59e84-116">When the method returns, `pcbSignature` will contain the number of bytes required for the `signature` array.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="59e84-117">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59e84-117">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59e84-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59e84-118">Requirements</span></span>  

 <span data-ttu-id="59e84-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59e84-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59e84-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="59e84-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="59e84-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59e84-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59e84-122">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59e84-122">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59e84-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59e84-123">See also</span></span>

- [<span data-ttu-id="59e84-124">GetTypeProps 메서드</span><span class="sxs-lookup"><span data-stu-id="59e84-124">GetTypeProps Method</span></span>](icordebugsymbolprovider-gettypeprops-method.md)
- [<span data-ttu-id="59e84-125">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59e84-125">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="59e84-126">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59e84-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
