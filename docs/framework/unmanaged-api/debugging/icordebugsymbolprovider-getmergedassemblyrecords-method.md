---
title: ICorDebugSymbolProvider::GetMergedAssemblyRecords 메서드
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
ms.openlocfilehash: b7d26fa80a7a8ebe7b4606b914c8cd09c52df1e4
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379629"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a><span data-ttu-id="343ea-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords 메서드</span><span class="sxs-lookup"><span data-stu-id="343ea-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords Method</span></span>
<span data-ttu-id="343ea-103">모든 병합된 어셈블리에 대한 기호 레코드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="343ea-103">Gets the symbol records for all the merged assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="343ea-104">구문</span><span class="sxs-lookup"><span data-stu-id="343ea-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="343ea-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="343ea-105">Parameters</span></span>  
 `cRequestedRecords`  
 <span data-ttu-id="343ea-106">[in] 요청되는 기호 레코드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="343ea-106">[in] The number of symbol records requested.</span></span>  
  
 `pcFetchedRecords`  
 <span data-ttu-id="343ea-107">[out] 메서드에 의해 검색되는 기호 레코드 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="343ea-107">[out] A pointer to the number of symbol records retrieved by the method.</span></span>  
  
 `pRecords`  
 <span data-ttu-id="343ea-108">[ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md) 개체의 배열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="343ea-108">A pointer to an array of [ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md) objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="343ea-109">설명</span><span class="sxs-lookup"><span data-stu-id="343ea-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="343ea-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="343ea-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="343ea-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="343ea-111">Requirements</span></span>  
 <span data-ttu-id="343ea-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="343ea-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="343ea-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="343ea-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="343ea-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="343ea-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="343ea-115">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="343ea-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="343ea-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="343ea-116">See also</span></span>

- [<span data-ttu-id="343ea-117">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="343ea-117">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="343ea-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="343ea-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
