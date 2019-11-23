---
title: IMetaDataImport::GetCustomAttributeByName 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeByName
helpviewer_keywords:
- IMetaDataImport::GetCustomAttributeByName method [.NET Framework metadata]
- GetCustomAttributeByName method [.NET Framework metadata]
ms.assetid: 909aa530-2e3b-4d0a-a38a-a2750e535d7d
topic_type:
- apiref
ms.openlocfilehash: bd7ba7ff10918e5953ea8ae89a60af3115af48a3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437691"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a><span data-ttu-id="6a1a9-102">IMetaDataImport::GetCustomAttributeByName 메서드</span><span class="sxs-lookup"><span data-stu-id="6a1a9-102">IMetaDataImport::GetCustomAttributeByName Method</span></span>
<span data-ttu-id="6a1a9-103">Gets the custom attribute, given its name and owner.</span><span class="sxs-lookup"><span data-stu-id="6a1a9-103">Gets the custom attribute, given its name and owner.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a1a9-104">구문</span><span class="sxs-lookup"><span data-stu-id="6a1a9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a1a9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6a1a9-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="6a1a9-106">[in] A metadata token representing the object that owns the custom attribute.</span><span class="sxs-lookup"><span data-stu-id="6a1a9-106">[in] A metadata token representing the object that owns the custom attribute.</span></span>  
  
 `szName`  
 <span data-ttu-id="6a1a9-107">[in] The name of the custom attribute.</span><span class="sxs-lookup"><span data-stu-id="6a1a9-107">[in] The name of the custom attribute.</span></span>  
  
 `ppData`  
 <span data-ttu-id="6a1a9-108">[out] A pointer to an array of data that is the value of the custom attribute.</span><span class="sxs-lookup"><span data-stu-id="6a1a9-108">[out] A pointer to an array of data that is the value of the custom attribute.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="6a1a9-109">[out] The size in bytes of the data returned in \*`ppData`.</span><span class="sxs-lookup"><span data-stu-id="6a1a9-109">[out] The size in bytes of the data returned in \*`ppData`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a1a9-110">주의</span><span class="sxs-lookup"><span data-stu-id="6a1a9-110">Remarks</span></span>  
 <span data-ttu-id="6a1a9-111">It is legal to define multiple custom attributes for the same owner; they may even have the same name.</span><span class="sxs-lookup"><span data-stu-id="6a1a9-111">It is legal to define multiple custom attributes for the same owner; they may even have the same name.</span></span> <span data-ttu-id="6a1a9-112">However, `GetCustomAttributeByName` returns only one instance.</span><span class="sxs-lookup"><span data-stu-id="6a1a9-112">However, `GetCustomAttributeByName` returns only one instance.</span></span> <span data-ttu-id="6a1a9-113">(`GetCustomAttributeByName` returns the first instance that it encounters.) To find all instances of a custom attribute, call the [IMetaDataImport::EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) method.</span><span class="sxs-lookup"><span data-stu-id="6a1a9-113">(`GetCustomAttributeByName` returns the first instance that it encounters.) To find all instances of a custom attribute, call the [IMetaDataImport::EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a1a9-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6a1a9-114">Requirements</span></span>  
 <span data-ttu-id="6a1a9-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6a1a9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a1a9-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6a1a9-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6a1a9-117">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6a1a9-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6a1a9-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a1a9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a1a9-119">참조</span><span class="sxs-lookup"><span data-stu-id="6a1a9-119">See also</span></span>

- [<span data-ttu-id="6a1a9-120">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a1a9-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="6a1a9-121">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a1a9-121">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
