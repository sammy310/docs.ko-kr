---
description: '자세히 알아보기: IMetaDataTables2:: GetMetaDataStreamInfo 메서드'
title: IMetaDataTables2::GetMetaDataStreamInfo 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStreamInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStreamInfo
helpviewer_keywords:
- GetMetaDataStreamInfo method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStreamInfo method [.NET Framework metadata]
ms.assetid: 8b280627-cc74-4789-95da-1fefc966de05
topic_type:
- apiref
ms.openlocfilehash: 323c31931cc97f18ff09df83c57153a3629d0a10
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799248"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a><span data-ttu-id="7b8a1-103">IMetaDataTables2::GetMetaDataStreamInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="7b8a1-103">IMetaDataTables2::GetMetaDataStreamInfo Method</span></span>

<span data-ttu-id="7b8a1-104">지정 된 인덱스에 있는 메타 데이터 스트림의 이름, 크기 및 내용을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-104">Gets the name, size, and contents of the metadata stream at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b8a1-105">구문</span><span class="sxs-lookup"><span data-stu-id="7b8a1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b8a1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7b8a1-106">Parameters</span></span>  

 `ix`  
 <span data-ttu-id="7b8a1-107">진행 요청 된 메타 데이터 스트림의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-107">[in] The index of the requested metadata stream.</span></span>  
  
 `ppchName`  
 <span data-ttu-id="7b8a1-108">제한이 스트림 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-108">[out] A pointer to the name of the stream.</span></span>  
  
 `ppv`  
 <span data-ttu-id="7b8a1-109">제한이 메타 데이터 스트림에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-109">[out] A pointer to the metadata stream.</span></span>  
  
 `pcb`  
 <span data-ttu-id="7b8a1-110">제한이 의 크기 (바이트)입니다 `ppv` .</span><span class="sxs-lookup"><span data-stu-id="7b8a1-110">[out] The size, in bytes, of `ppv`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b8a1-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7b8a1-111">Requirements</span></span>  

 <span data-ttu-id="7b8a1-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b8a1-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="7b8a1-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7b8a1-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b8a1-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7b8a1-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b8a1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b8a1-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b8a1-116">See also</span></span>

- [<span data-ttu-id="7b8a1-117">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b8a1-117">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
- [<span data-ttu-id="7b8a1-118">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7b8a1-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
