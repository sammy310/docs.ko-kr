---
title: ICorDebugDataTarget2::GetSymbolProviderForImage 메서드
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
ms.openlocfilehash: 5a5ccaeb36dcda82c0189026e19c6a7c023f3e1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713771"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="42990-102">ICorDebugDataTarget2::GetSymbolProviderForImage 메서드</span><span class="sxs-lookup"><span data-stu-id="42990-102">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>

<span data-ttu-id="42990-103">모듈의 시스템 공급자를 해당 모듈의 기본 주소에서 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="42990-103">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42990-104">구문</span><span class="sxs-lookup"><span data-stu-id="42990-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42990-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="42990-105">Parameters</span></span>  

 `imageBaseAddress`  
 <span data-ttu-id="42990-106">진행 모듈의 기준 주소를 나타내는 [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="42990-106">[in] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="42990-107">제한이 [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="42990-107">[out] A pointer to the address of an [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42990-108">설명</span><span class="sxs-lookup"><span data-stu-id="42990-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="42990-109">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42990-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42990-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="42990-110">Requirements</span></span>  

 <span data-ttu-id="42990-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="42990-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42990-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42990-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42990-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42990-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42990-114">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42990-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42990-115">참조</span><span class="sxs-lookup"><span data-stu-id="42990-115">See also</span></span>

- [<span data-ttu-id="42990-116">ICorDebugDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="42990-116">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="42990-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="42990-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
