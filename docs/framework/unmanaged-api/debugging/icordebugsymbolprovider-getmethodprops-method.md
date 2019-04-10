---
title: ICorDebugSymbolProvider::GetMethodProps 메서드
ms.date: 03/30/2017
ms.assetid: 8f836b80-b7a5-460b-bf76-5f0e45652aea
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 784fcb10e9c0c3c6ff50c25d47bb4fb3fd5762ba
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59161111"
---
# <a name="icordebugsymbolprovidergetmethodprops-method"></a><span data-ttu-id="219a2-102">ICorDebugSymbolProvider::GetMethodProps 메서드</span><span class="sxs-lookup"><span data-stu-id="219a2-102">ICorDebugSymbolProvider::GetMethodProps Method</span></span>
<span data-ttu-id="219a2-103">해당 메서드에 RVA(상대 가상 주소)가 제공된 경우 메서드의 메타데이터 토큰 및 제네릭 매개 변수 정보와 같은 메서드 속성 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="219a2-103">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="219a2-104">구문</span><span class="sxs-lookup"><span data-stu-id="219a2-104">Syntax</span></span>  
  
```  
HRESULT GetMethodProps(  
   [in]  ULONG32 codeRva,  
   [out] mdToken *pMethodToken,  
   [out] ULONG32 *pcGenericParams,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="219a2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="219a2-105">Parameters</span></span>  
 `codeRVA`  
 <span data-ttu-id="219a2-106">[in] 정보를 검색할 메서드의 상대 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="219a2-106">[in] A relative virtual address in the method about which information is to be retrieved.</span></span>  
  
 `pMethodToken`  
 <span data-ttu-id="219a2-107">[out] 메서드의 메타데이터 토큰에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="219a2-107">[out] A pointer to the method's metadata token.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="219a2-108">[out] 이 메서드와 연결된 제네릭 매개 변수 개수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="219a2-108">[out] A pointer to the number of generic parameters associated with this method.</span></span>  
  
 `cbSignature`  
 <span data-ttu-id="219a2-109">[in] `signature` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="219a2-109">[in] The size of the `signature` array.</span></span> <span data-ttu-id="219a2-110">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="219a2-110">See the Remarks section.</span></span>  
  
 `pcbSignature`  
 <span data-ttu-id="219a2-111">[out] 반환된 `signature` 배열의 크기에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="219a2-111">[out] A pointer to the size of the returned `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="219a2-112">[out] 모든 제네릭 매개 변수의 typespec 서명을 보유하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="219a2-112">[out] A buffer that holds the typespec signatures of all generic parameters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="219a2-113">설명</span><span class="sxs-lookup"><span data-stu-id="219a2-113">Remarks</span></span>  
 <span data-ttu-id="219a2-114">필요한 크기의 메서드를 가져오려고 `signature` 배열, 설정 합니다 `cbSignature` 인수를 0 및 `signature` 를 **null**합니다.</span><span class="sxs-lookup"><span data-stu-id="219a2-114">To get the required size of the method's `signature` array, set the `cbSignature` argument to 0 and `signature` to **null**.</span></span> <span data-ttu-id="219a2-115">메서드가 반환되면 `signature` 배열에 필요한 바이트 수가 `pcbSignature`에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="219a2-115">When the method returns, `pcbSignature` will contain the number of bytes required for the `signature` array.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="219a2-116">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="219a2-116">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="219a2-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="219a2-117">Requirements</span></span>  
 <span data-ttu-id="219a2-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="219a2-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="219a2-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="219a2-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="219a2-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="219a2-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="219a2-121">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="219a2-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="219a2-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="219a2-122">See also</span></span>

- [<span data-ttu-id="219a2-123">GetTypeProps 메서드</span><span class="sxs-lookup"><span data-stu-id="219a2-123">GetTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)
- [<span data-ttu-id="219a2-124">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="219a2-124">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="219a2-125">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="219a2-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
