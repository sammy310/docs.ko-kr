---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9b3c9b879faf49ec7a485641c622d40a684dfb35
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469302"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="0f153-102">IMetaDataImport::GetFieldMarshal 메서드</span><span class="sxs-lookup"><span data-stu-id="0f153-102">IMetaDataImport::GetFieldMarshal Method</span></span>
<span data-ttu-id="0f153-103">지정 된 필드 메타 데이터 토큰이 나타내는 필드의 네이티브, 관리 되지 않는 형식에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f153-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f153-104">구문</span><span class="sxs-lookup"><span data-stu-id="0f153-104">Syntax</span></span>  
  
```  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,   
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f153-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0f153-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="0f153-106">[in] Interop 마샬링 정보를 가져올 필드를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0f153-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="0f153-107">[out] 메타 데이터 서명의 필드의 네이티브 형식에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0f153-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="0f153-108">[out] 크기 (바이트) `ppvNativeType`합니다.</span><span class="sxs-lookup"><span data-stu-id="0f153-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f153-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0f153-109">Requirements</span></span>  
 <span data-ttu-id="0f153-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0f153-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f153-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0f153-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0f153-112">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0f153-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0f153-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f153-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f153-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="0f153-114">See also</span></span>
- [<span data-ttu-id="0f153-115">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f153-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0f153-116">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f153-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
