---
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
ms.openlocfilehash: 9a088c7e4e9c72c8247ccdd384bc724587210c37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710872"
---
# <a name="icordebugmdagetxml-method"></a><span data-ttu-id="50a74-102">ICorDebugMDA::GetXML 메서드</span><span class="sxs-lookup"><span data-stu-id="50a74-102">ICorDebugMDA::GetXML Method</span></span>

<span data-ttu-id="50a74-103">[ICorDebugMDA](icordebugmda-interface.md)로 표시 된 MDA (관리 디버깅 도우미)와 연결 된 전체 XML 스트림을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="50a74-103">Gets the full XML stream associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50a74-104">구문</span><span class="sxs-lookup"><span data-stu-id="50a74-104">Syntax</span></span>  
  
```cpp  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50a74-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="50a74-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="50a74-106">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="50a74-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="50a74-107">제한이 XML 스트림의 길이에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="50a74-107">[out] A pointer to the length of the XML stream.</span></span>  
  
 `szName`  
 <span data-ttu-id="50a74-108">제한이 XML 스트림을 저장할 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="50a74-108">[out] An array in which to store the XML stream.</span></span> <span data-ttu-id="50a74-109">배열은 비어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50a74-109">The array may be empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50a74-110">설명</span><span class="sxs-lookup"><span data-stu-id="50a74-110">Remarks</span></span>  

 <span data-ttu-id="50a74-111">`GetXML`메서드는 연결 된 XML 스트림의 크기에 따라 성능에 잠재적으로 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50a74-111">The `GetXML` method can potentially affect performance, depending on the size of the associated XML stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50a74-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="50a74-112">Requirements</span></span>  

 <span data-ttu-id="50a74-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50a74-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50a74-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50a74-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50a74-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50a74-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50a74-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50a74-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50a74-117">참조</span><span class="sxs-lookup"><span data-stu-id="50a74-117">See also</span></span>

- [<span data-ttu-id="50a74-118">ICorDebugMDA 인터페이스</span><span class="sxs-lookup"><span data-stu-id="50a74-118">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="50a74-119">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="50a74-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
