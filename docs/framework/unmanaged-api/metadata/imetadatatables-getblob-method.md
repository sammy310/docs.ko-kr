---
title: IMetaDataTables::GetBlob 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlob
helpviewer_keywords:
- GetBlob method [.NET Framework metadata]
- IMetaDataTables::GetBlob method [.NET Framework metadata]
ms.assetid: 94667c1c-6d58-4aa7-b74e-530b11e2a276
topic_type:
- apiref
ms.openlocfilehash: 32f32625ee40d50249ce3e009add543c4137b196
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726472"
---
# <a name="imetadatatablesgetblob-method"></a><span data-ttu-id="da95f-102">IMetaDataTables::GetBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="da95f-102">IMetaDataTables::GetBlob Method</span></span>

<span data-ttu-id="da95f-103">지정 된 열 인덱스에 있는 BLOB (binary large object)에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="da95f-103">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da95f-104">구문</span><span class="sxs-lookup"><span data-stu-id="da95f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlob (  
    [in]  ULONG          ixBlob,  
    [out] ULONG          *pcbData,  
    [out] const void     **ppData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da95f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="da95f-105">Parameters</span></span>  

 `ixBlob`  
 <span data-ttu-id="da95f-106">진행 가져올 메모리 주소 `ppData` 입니다.</span><span class="sxs-lookup"><span data-stu-id="da95f-106">[in] The memory address from which to get `ppData`.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="da95f-107">제한이 의 크기 (바이트)에 대 한 포인터입니다 `ppData` .</span><span class="sxs-lookup"><span data-stu-id="da95f-107">[out] A pointer to the size, in bytes, of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="da95f-108">제한이 검색 된 이진 데이터에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="da95f-108">[out] A pointer to a pointer to the binary data retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da95f-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="da95f-109">Requirements</span></span>  

 <span data-ttu-id="da95f-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da95f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da95f-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="da95f-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="da95f-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da95f-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="da95f-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da95f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da95f-114">참조</span><span class="sxs-lookup"><span data-stu-id="da95f-114">See also</span></span>

- [<span data-ttu-id="da95f-115">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="da95f-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="da95f-116">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="da95f-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
