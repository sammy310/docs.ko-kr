---
description: '자세히 알아보기: ICorDebugInstanceFieldSymbol:: GetName 메서드'
title: ICorDebugInstanceFieldSymbol::GetName 메서드
ms.date: 03/30/2017
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
ms.openlocfilehash: 9cc2106d1527aa0b4d9e5c52115b703ffe55037f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791194"
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="8e685-103">ICorDebugInstanceFieldSymbol::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="8e685-103">ICorDebugInstanceFieldSymbol::GetName Method</span></span>

<span data-ttu-id="8e685-104">인스턴스 필드의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8e685-104">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e685-105">구문</span><span class="sxs-lookup"><span data-stu-id="8e685-105">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e685-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8e685-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="8e685-107">[in] `szName` 버퍼의 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8e685-107">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="8e685-108">[out] `szName` 버퍼에 실제로 기록된 문자 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8e685-108">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="8e685-109">[out] 반환된 이름을 저장하는 문자 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="8e685-109">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e685-110">설명</span><span class="sxs-lookup"><span data-stu-id="8e685-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8e685-111">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e685-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e685-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8e685-112">Requirements</span></span>  

 <span data-ttu-id="8e685-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e685-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e685-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e685-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e685-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e685-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e685-116">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e685-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e685-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e685-117">See also</span></span>

- [<span data-ttu-id="8e685-118">ICorDebugInstanceFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e685-118">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="8e685-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e685-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
