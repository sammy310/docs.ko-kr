---
title: ICorPublishProcess::GetDisplayName 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetDisplayName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetDisplayName
helpviewer_keywords:
- ICorPublishProcess::GetDisplayName method [.NET Framework debugging]
- GetDisplayName method, ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 7c0af9e9-a73f-41aa-a685-b21c439e059d
topic_type:
- apiref
ms.openlocfilehash: 5a037695892252042d7827165595f7bad0feba56
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693166"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="b4b5c-102">ICorPublishProcess::GetDisplayName 메서드</span><span class="sxs-lookup"><span data-stu-id="b4b5c-102">ICorPublishProcess::GetDisplayName Method</span></span>

<span data-ttu-id="b4b5c-103">이 [ICorPublishProcess](icorpublishprocess-interface.md)에서 참조 하는 프로세스에 대 한 실행 파일의 전체 경로를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4b5c-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4b5c-104">구문</span><span class="sxs-lookup"><span data-stu-id="b4b5c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4b5c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b4b5c-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="b4b5c-106">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="b4b5c-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="b4b5c-107">제한이 배열에 반환 된 와이드 문자의 수입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="b4b5c-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="b4b5c-108">제한이 실행 파일의 전체 경로를 포함 하 여 이름을 저장 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b4b5c-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="b4b5c-109">이름이 null로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4b5c-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4b5c-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b4b5c-110">Requirements</span></span>  

 <span data-ttu-id="b4b5c-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b4b5c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4b5c-112">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="b4b5c-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="b4b5c-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4b5c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4b5c-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4b5c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4b5c-115">참조</span><span class="sxs-lookup"><span data-stu-id="b4b5c-115">See also</span></span>

- [<span data-ttu-id="b4b5c-116">ICorPublishProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4b5c-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
