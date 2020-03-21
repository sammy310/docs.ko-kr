---
title: ICorDebugAppDomain::GetName 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type:
- apiref
ms.openlocfilehash: 45d27fca888bdabedf197525c63dbd03af7ba1ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179084"
---
# <a name="icordebugappdomaingetname-method"></a><span data-ttu-id="16af2-102">ICorDebugAppDomain::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="16af2-102">ICorDebugAppDomain::GetName Method</span></span>
<span data-ttu-id="16af2-103">응용 프로그램 도메인의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="16af2-103">Gets the name of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16af2-104">구문</span><span class="sxs-lookup"><span data-stu-id="16af2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
         WCHAR              szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16af2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="16af2-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="16af2-106">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="16af2-106">[in] The size of the `szName` array.</span></span> <span data-ttu-id="16af2-107">이 값을 0으로 설정하여 이 메서드를 쿼리 모드에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="16af2-107">Set this value to zero to put this method in query mode.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="16af2-108">【아웃】 이름 크기 또는 실제로 반환된 문자 수에 `szName`대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="16af2-108">[out] A pointer to the size of the name or the number of characters actually returned in `szName`.</span></span> <span data-ttu-id="16af2-109">쿼리 모드에서 이 값을 사용하면 호출자가 이름에 할당할 버퍼의 큰 정도를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16af2-109">In query mode, this value lets the caller know how large a buffer to allocate for the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="16af2-110">【아웃】 응용 프로그램 도메인의 이름을 저장하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="16af2-110">[out] An array that stores the name of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16af2-111">설명</span><span class="sxs-lookup"><span data-stu-id="16af2-111">Remarks</span></span>  
 <span data-ttu-id="16af2-112">디버거는 `GetName` 이름에 필요한 버퍼의 크기를 얻기 위해 메서드를 한 번 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="16af2-112">A debugger calls the `GetName` method once to get the size of a buffer needed for the name.</span></span> <span data-ttu-id="16af2-113">디버거는 버퍼를 할당한 다음 메서드를 두 번째로 호출하여 버퍼를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="16af2-113">The debugger allocates the buffer, and then calls the method a second time to fill the buffer.</span></span> <span data-ttu-id="16af2-114">이름의 크기를 얻기 위해 첫 번째 호출을 *쿼리 모드라고*합니다.</span><span class="sxs-lookup"><span data-stu-id="16af2-114">The first call, to get the size of the name, is referred to as *query mode*.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16af2-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="16af2-115">Requirements</span></span>  
 <span data-ttu-id="16af2-116">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16af2-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16af2-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16af2-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16af2-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16af2-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16af2-119">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16af2-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
