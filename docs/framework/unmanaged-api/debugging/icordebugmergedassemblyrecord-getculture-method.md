---
description: '자세히 알아보기: ICorDebugMergedAssemblyRecord:: GetCulture 메서드'
title: ICorDebugMergedAssemblyRecord::GetCulture 메서드
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
ms.openlocfilehash: f530bb68a1e7e4c4bff53b8f3046f6ae9ca42aab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754006"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a><span data-ttu-id="3d036-103">ICorDebugMergedAssemblyRecord::GetCulture 메서드</span><span class="sxs-lookup"><span data-stu-id="3d036-103">ICorDebugMergedAssemblyRecord::GetCulture Method</span></span>

<span data-ttu-id="3d036-104">어셈블리의 문화권 이름 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3d036-104">Gets the culture name string of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d036-105">구문</span><span class="sxs-lookup"><span data-stu-id="3d036-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,
   [out] ULONG32 *pcchCulture,
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d036-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3d036-106">Parameters</span></span>  

 `cchCulture`  
 <span data-ttu-id="3d036-107">[in] `szCulture` 버퍼의 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3d036-107">[in] The number of characters in the `szCulture` buffer.</span></span>  
  
 `pcchCulture`  
 <span data-ttu-id="3d036-108">[out] 실제로 `szCulture` 버퍼에 기록되는 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3d036-108">[out] The number of characters actually written to the `szCulture` buffer.</span></span>  
  
 `szCulture`  
 <span data-ttu-id="3d036-109">[out] 문화권 이름을 포함하는 문자 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="3d036-109">[out] A character array that contains the culture name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d036-110">설명</span><span class="sxs-lookup"><span data-stu-id="3d036-110">Remarks</span></span>  

 <span data-ttu-id="3d036-111">문화권 이름은 문화권을 식별하는 고유 문자열입니다(예: 영어(미국) 문화권 "en-US" 또는 중립 문화권 "neutral").</span><span class="sxs-lookup"><span data-stu-id="3d036-111">The culture name is a unique string that identifies a culture, such as "en-US" (for the English (United States) culture), or "neutral" (for a neutral culture).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3d036-112">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d036-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d036-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3d036-113">Requirements</span></span>  

 <span data-ttu-id="3d036-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d036-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d036-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d036-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d036-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d036-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d036-117">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d036-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d036-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d036-118">See also</span></span>

- [<span data-ttu-id="3d036-119">ICorDebugMergedAssemblyRecord 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3d036-119">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="3d036-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3d036-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
