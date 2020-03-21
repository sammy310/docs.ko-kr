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
ms.openlocfilehash: 91a19e5e15dddd446208dfa3b2c32826282067eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175397"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="bddbd-102">IMetaDataImport::GetFieldMarshal 메서드</span><span class="sxs-lookup"><span data-stu-id="bddbd-102">IMetaDataImport::GetFieldMarshal Method</span></span>
<span data-ttu-id="bddbd-103">지정된 필드 메타데이터 토큰으로 표시되는 관리되지 않는 네이티브 필드 형식에 대한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bddbd-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bddbd-104">구문</span><span class="sxs-lookup"><span data-stu-id="bddbd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bddbd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bddbd-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="bddbd-106">【인】 필드를 나타내는 메타데이터 토큰으로 인터옵 마샬링 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bddbd-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="bddbd-107">【아웃】 필드의 네이티브 형식의 메타데이터 시그니처에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bddbd-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="bddbd-108">【아웃】 의 바이트 크기입니다. `ppvNativeType`</span><span class="sxs-lookup"><span data-stu-id="bddbd-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bddbd-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bddbd-109">Requirements</span></span>  
 <span data-ttu-id="bddbd-110">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bddbd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bddbd-111">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="bddbd-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bddbd-112">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="bddbd-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bddbd-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bddbd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bddbd-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bddbd-114">See also</span></span>

- [<span data-ttu-id="bddbd-115">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bddbd-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="bddbd-116">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bddbd-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
