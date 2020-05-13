---
title: ICorDebugInstanceFieldSymbol::GetName 메서드
ms.date: 03/30/2017
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
ms.openlocfilehash: 0f1b648f494a2f2676374cfd13db46b70f1f195c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209996"
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="681ff-102">ICorDebugInstanceFieldSymbol::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="681ff-102">ICorDebugInstanceFieldSymbol::GetName Method</span></span>
<span data-ttu-id="681ff-103">인스턴스 필드의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="681ff-103">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="681ff-104">구문</span><span class="sxs-lookup"><span data-stu-id="681ff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="681ff-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="681ff-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="681ff-106">[in] `szName` 버퍼의 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="681ff-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="681ff-107">[out] `szName` 버퍼에 실제로 기록된 문자 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="681ff-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="681ff-108">[out] 반환된 이름을 저장하는 문자 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="681ff-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="681ff-109">설명</span><span class="sxs-lookup"><span data-stu-id="681ff-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="681ff-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="681ff-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="681ff-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="681ff-111">Requirements</span></span>  
 <span data-ttu-id="681ff-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="681ff-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="681ff-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="681ff-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="681ff-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="681ff-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="681ff-115">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="681ff-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="681ff-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="681ff-116">See also</span></span>

- [<span data-ttu-id="681ff-117">ICorDebugInstanceFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="681ff-117">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="681ff-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="681ff-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
