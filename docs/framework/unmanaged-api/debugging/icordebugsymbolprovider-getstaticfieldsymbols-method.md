---
description: '자세히 알아보기: ICorDebugSymbolProvider:: GetStaticFieldSymbols 메서드'
title: ICorDebugSymbolProvider::GetStaticFieldSymbols 메서드
ms.date: 03/30/2017
ms.assetid: b178367f-a6e4-413c-b06f-daf3804b456b
ms.openlocfilehash: e95f77be86ef88a73ca4c833b242617a0d405e21
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659710"
---
# <a name="icordebugsymbolprovidergetstaticfieldsymbols-method"></a><span data-ttu-id="5bdf0-103">ICorDebugSymbolProvider::GetStaticFieldSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="5bdf0-103">ICorDebugSymbolProvider::GetStaticFieldSymbols Method</span></span>

<span data-ttu-id="5bdf0-104">typespec 서명에 해당하는 정적 필드 기호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5bdf0-104">Gets the static field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bdf0-105">구문</span><span class="sxs-lookup"><span data-stu-id="5bdf0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugStaticFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bdf0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5bdf0-106">Parameters</span></span>  

 `cbSignature`  
 <span data-ttu-id="5bdf0-107">[in] `typeSig` 배열의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5bdf0-107">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="5bdf0-108">[in] `typespec` 서명이 들어 있는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="5bdf0-108">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="5bdf0-109">[in] 요청된 기호 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5bdf0-109">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="5bdf0-110">[out] 메서드에 의해 검색되는 기호 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5bdf0-110">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="5bdf0-111">제한이 요청 된 정적 필드 기호를 포함 하는 [ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md) 배열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5bdf0-111">[out] A pointer to an [ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md) array that contains the requested static field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bdf0-112">설명</span><span class="sxs-lookup"><span data-stu-id="5bdf0-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5bdf0-113">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdf0-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bdf0-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5bdf0-114">Requirements</span></span>  

 <span data-ttu-id="5bdf0-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5bdf0-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bdf0-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5bdf0-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5bdf0-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5bdf0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5bdf0-118">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bdf0-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bdf0-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5bdf0-119">See also</span></span>

- [<span data-ttu-id="5bdf0-120">GetInstanceFieldSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="5bdf0-120">GetInstanceFieldSymbols Method</span></span>](icordebugsymbolprovider-getinstancefieldsymbols-method.md)
- [<span data-ttu-id="5bdf0-121">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5bdf0-121">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="5bdf0-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5bdf0-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
