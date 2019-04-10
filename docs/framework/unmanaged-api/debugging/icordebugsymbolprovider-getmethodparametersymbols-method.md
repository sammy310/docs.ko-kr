---
title: ICorDebugSymbolProvider::GetMethodParameterSymbols 메서드
ms.date: 03/30/2017
ms.assetid: 58b7c0b9-f6ad-4b49-b92d-0e421cfd0ec6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 98efd1446c88c3a6c004b5a3254c9db835a43804
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197375"
---
# <a name="icordebugsymbolprovidergetmethodparametersymbols-method"></a><span data-ttu-id="12202-102">ICorDebugSymbolProvider::GetMethodParameterSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="12202-102">ICorDebugSymbolProvider::GetMethodParameterSymbols Method</span></span>
<span data-ttu-id="12202-103">메서드의 RVA(상대 가상 주소)가 지정된 경우 해당 메서드의 매개 변수 기호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="12202-103">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12202-104">구문</span><span class="sxs-lookup"><span data-stu-id="12202-104">Syntax</span></span>  
  
```  
HRESULT GetMethodParameterSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12202-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="12202-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="12202-106">[in] 메서드의 기본 상대 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="12202-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="12202-107">[in] 요청되는 로컬 기호 수입니다.</span><span class="sxs-lookup"><span data-stu-id="12202-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="12202-108">[out] 메서드에 의해 검색되는 기호 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="12202-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="12202-109">[out] 에 대 한 포인터를 [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) 메서드의 로컬 기호를 포함 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="12202-109">[out] A pointer to an [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12202-110">설명</span><span class="sxs-lookup"><span data-stu-id="12202-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12202-111">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12202-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12202-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="12202-112">Requirements</span></span>  
 <span data-ttu-id="12202-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="12202-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12202-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="12202-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12202-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12202-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="12202-116">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="12202-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="12202-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="12202-117">See also</span></span>

- [<span data-ttu-id="12202-118">GetMethodLocalSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="12202-118">GetMethodLocalSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodlocalsymbols-method.md)
- [<span data-ttu-id="12202-119">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12202-119">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="12202-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12202-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
