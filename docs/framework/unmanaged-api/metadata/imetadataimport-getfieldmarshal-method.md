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
ms.openlocfilehash: 35f73135dbeea1c79d15e0a9e9367c5d533487ce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676865"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="aaafd-102">IMetaDataImport::GetFieldMarshal 메서드</span><span class="sxs-lookup"><span data-stu-id="aaafd-102">IMetaDataImport::GetFieldMarshal Method</span></span>

<span data-ttu-id="aaafd-103">지정 된 필드 메타 데이터 토큰이 나타내는 필드의 관리 되지 않는 네이티브 형식에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="aaafd-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaafd-104">구문</span><span class="sxs-lookup"><span data-stu-id="aaafd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aaafd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="aaafd-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="aaafd-106">진행 Interop 마샬링 정보를 가져올 필드를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="aaafd-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="aaafd-107">제한이 필드의 네이티브 형식에 대 한 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aaafd-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="aaafd-108">제한이 의 크기 (바이트) `ppvNativeType` 입니다.</span><span class="sxs-lookup"><span data-stu-id="aaafd-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aaafd-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aaafd-109">Requirements</span></span>  

 <span data-ttu-id="aaafd-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aaafd-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aaafd-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="aaafd-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aaafd-112">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaafd-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="aaafd-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aaafd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaafd-114">참조</span><span class="sxs-lookup"><span data-stu-id="aaafd-114">See also</span></span>

- [<span data-ttu-id="aaafd-115">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aaafd-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="aaafd-116">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aaafd-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
