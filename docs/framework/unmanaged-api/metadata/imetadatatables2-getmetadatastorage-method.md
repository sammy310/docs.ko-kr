---
title: IMetaDataTables2::GetMetaDataStorage 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStorage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStorage
helpviewer_keywords:
- GetMetaDataStorage method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStorage method [.NET Framework metadata]
ms.assetid: 667a6d1e-753d-4ea2-8fd8-a8337d1bb9cd
topic_type:
- apiref
ms.openlocfilehash: 55fcde6c47705e515eb2d20f25ac870e257b92c0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501133"
---
# <a name="imetadatatables2getmetadatastorage-method"></a><span data-ttu-id="d8e2f-102">IMetaDataTables2::GetMetaDataStorage 메서드</span><span class="sxs-lookup"><span data-stu-id="d8e2f-102">IMetaDataTables2::GetMetaDataStorage Method</span></span>
<span data-ttu-id="d8e2f-103">지정 된 섹션에 저장 된 메타 데이터의 크기와 내용을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-103">Gets the size and contents of the metadata stored in the specified section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8e2f-104">구문</span><span class="sxs-lookup"><span data-stu-id="d8e2f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataStorage (  
   [in, out] const void   **ppvMd,  
   [out] ULONG   *pcbMd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8e2f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d8e2f-105">Parameters</span></span>  
 `ppvMd`  
 <span data-ttu-id="d8e2f-106">[in, out] 메타 데이터 섹션에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-106">[in, out] A pointer to a metadata section.</span></span>  
  
 `pcbMd`  
 <span data-ttu-id="d8e2f-107">제한이 메타 데이터 스트림의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-107">[out] The size of the metadata stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8e2f-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d8e2f-108">Requirements</span></span>  
 <span data-ttu-id="d8e2f-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8e2f-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="d8e2f-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d8e2f-111">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8e2f-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d8e2f-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8e2f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8e2f-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8e2f-113">See also</span></span>

- [<span data-ttu-id="d8e2f-114">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8e2f-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
- [<span data-ttu-id="d8e2f-115">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d8e2f-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
