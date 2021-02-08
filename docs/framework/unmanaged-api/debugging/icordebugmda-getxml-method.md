---
description: '자세히 알아보기: ICorDebugMDA:: GetXML 메서드'
title: ICorDebugMDA::GetXML 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetXML
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetXML
helpviewer_keywords:
- ICorDebugMDA::GetXML method [.NET Framework debugging]
- GetXML method [.NET Framework debugging]
ms.assetid: 29746b24-3766-4255-8813-0426c45e73e5
topic_type:
- apiref
ms.openlocfilehash: fa506e6e8f306271f10a7a715af9b8bc6a80c1d6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801139"
---
# <a name="icordebugmdagetxml-method"></a><span data-ttu-id="1ccaa-103">ICorDebugMDA::GetXML 메서드</span><span class="sxs-lookup"><span data-stu-id="1ccaa-103">ICorDebugMDA::GetXML Method</span></span>

<span data-ttu-id="1ccaa-104">[ICorDebugMDA](icordebugmda-interface.md)로 표시 된 MDA (관리 디버깅 도우미)와 연결 된 전체 XML 스트림을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1ccaa-104">Gets the full XML stream associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ccaa-105">구문</span><span class="sxs-lookup"><span data-stu-id="1ccaa-105">Syntax</span></span>  
  
```cpp  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ccaa-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1ccaa-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="1ccaa-107">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="1ccaa-107">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="1ccaa-108">제한이 XML 스트림의 길이에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1ccaa-108">[out] A pointer to the length of the XML stream.</span></span>  
  
 `szName`  
 <span data-ttu-id="1ccaa-109">제한이 XML 스트림을 저장할 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="1ccaa-109">[out] An array in which to store the XML stream.</span></span> <span data-ttu-id="1ccaa-110">배열은 비어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ccaa-110">The array may be empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ccaa-111">설명</span><span class="sxs-lookup"><span data-stu-id="1ccaa-111">Remarks</span></span>  

 <span data-ttu-id="1ccaa-112">`GetXML`메서드는 연결 된 XML 스트림의 크기에 따라 성능에 잠재적으로 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ccaa-112">The `GetXML` method can potentially affect performance, depending on the size of the associated XML stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ccaa-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ccaa-113">Requirements</span></span>  

 <span data-ttu-id="1ccaa-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1ccaa-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ccaa-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1ccaa-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1ccaa-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ccaa-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ccaa-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ccaa-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ccaa-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1ccaa-118">See also</span></span>

- [<span data-ttu-id="1ccaa-119">ICorDebugMDA 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ccaa-119">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="1ccaa-120">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="1ccaa-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
