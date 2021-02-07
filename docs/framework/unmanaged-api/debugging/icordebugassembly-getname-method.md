---
description: '자세히 알아보기: ICorDebugAssembly:: GetName 메서드'
title: ICorDebugAssembly::GetName 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetName
helpviewer_keywords:
- ICorDebugAssembly::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: cdeda721-b214-4503-a291-c70b68b5f36b
topic_type:
- apiref
ms.openlocfilehash: c2ffa910eaf97c5539a33dbcd3486b7dfb117b51
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711988"
---
# <a name="icordebugassemblygetname-method"></a><span data-ttu-id="bd2d1-103">ICorDebugAssembly::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="bd2d1-103">ICorDebugAssembly::GetName Method</span></span>

<span data-ttu-id="bd2d1-104">이 인스턴스가 나타내는 어셈블리의 이름을 가져옵니다 `ICorDebugAssembly` .</span><span class="sxs-lookup"><span data-stu-id="bd2d1-104">Gets the name of the assembly that this `ICorDebugAssembly` instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd2d1-105">구문</span><span class="sxs-lookup"><span data-stu-id="bd2d1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd2d1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bd2d1-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="bd2d1-107">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="bd2d1-107">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="bd2d1-108">제한이 이름의 실제 길이를 지정 하는 정수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bd2d1-108">[out] A pointer to an integer that specifies the actual length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="bd2d1-109">제한이 이름을 저장 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="bd2d1-109">[out] An array that stores the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd2d1-110">설명</span><span class="sxs-lookup"><span data-stu-id="bd2d1-110">Remarks</span></span>  

 <span data-ttu-id="bd2d1-111">`GetName`메서드는 어셈블리의 전체 경로 및 파일 이름을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2d1-111">The `GetName` method returns the full path and file name of the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd2d1-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bd2d1-112">Requirements</span></span>  

 <span data-ttu-id="bd2d1-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bd2d1-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd2d1-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bd2d1-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bd2d1-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd2d1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd2d1-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd2d1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
