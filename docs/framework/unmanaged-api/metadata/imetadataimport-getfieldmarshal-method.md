---
description: '자세히 알아보기: IMetaDataImport:: GetFieldMarshal 메서드'
title: IMetaDataImport::GetFieldMarshal 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldMarshal
helpviewer_keywords:
- GetFieldMarshal method [.NET Framework metadata]
- IMetaDataImport::GetFieldMarshal method [.NET Framework metadata]
ms.assetid: 4e2d88c6-8a3a-4fbe-900b-b4f4c06bf6bf
topic_type:
- apiref
ms.openlocfilehash: d6ca1f80a8b9bae4d9c02466042300bc3662f7c3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803518"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="4660f-103">IMetaDataImport::GetFieldMarshal 메서드</span><span class="sxs-lookup"><span data-stu-id="4660f-103">IMetaDataImport::GetFieldMarshal Method</span></span>

<span data-ttu-id="4660f-104">지정 된 필드 메타 데이터 토큰이 나타내는 필드의 관리 되지 않는 네이티브 형식에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4660f-104">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4660f-105">구문</span><span class="sxs-lookup"><span data-stu-id="4660f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4660f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4660f-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="4660f-107">진행 Interop 마샬링 정보를 가져올 필드를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="4660f-107">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="4660f-108">제한이 필드의 네이티브 형식에 대 한 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4660f-108">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="4660f-109">제한이 의 크기 (바이트) `ppvNativeType` 입니다.</span><span class="sxs-lookup"><span data-stu-id="4660f-109">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4660f-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4660f-110">Requirements</span></span>  

 <span data-ttu-id="4660f-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4660f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4660f-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="4660f-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4660f-113">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4660f-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4660f-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4660f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4660f-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4660f-115">See also</span></span>

- [<span data-ttu-id="4660f-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4660f-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="4660f-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4660f-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
