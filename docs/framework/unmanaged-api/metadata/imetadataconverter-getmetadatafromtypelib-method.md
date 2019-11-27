---
title: IMetaDataConverter::GetMetaDataFromTypeLib 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetMetaDataFromTypeLib
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib
helpviewer_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib method [.NET Framework metadata]
- GetMetaDataFromTypeLib method [.NET Framework metadata]
ms.assetid: 97dc3a56-adfa-431f-889e-06a35ac84d51
topic_type:
- apiref
ms.openlocfilehash: 6391e819d53c3ed8f0d596b15c4a2bb268f72fd5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436276"
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a><span data-ttu-id="7c40a-102">IMetaDataConverter::GetMetaDataFromTypeLib 메서드</span><span class="sxs-lookup"><span data-stu-id="7c40a-102">IMetaDataConverter::GetMetaDataFromTypeLib Method</span></span>
<span data-ttu-id="7c40a-103">지정 된 `ITypeLib` 인스턴스로 표시 되는 형식 라이브러리의 메타 데이터 서명을 나타내는 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7c40a-103">Gets an interface pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library represented by the specified `ITypeLib` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c40a-104">구문</span><span class="sxs-lookup"><span data-stu-id="7c40a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,   
    [out] IMetaDataImport **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c40a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7c40a-105">Parameters</span></span>  
 `pITL`  
 <span data-ttu-id="7c40a-106">진행 형식 라이브러리를 나타내는 `ITypeLib` 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7c40a-106">[in] Pointer to an `ITypeLib` object that represents the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="7c40a-107">제한이 메타 데이터 서명을 나타내는 `IMetaDataImport` 인스턴스의 주소를 수신 하는 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7c40a-107">[out] Pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c40a-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c40a-108">Requirements</span></span>  
 <span data-ttu-id="7c40a-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7c40a-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c40a-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="7c40a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7c40a-111">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c40a-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7c40a-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c40a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c40a-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c40a-113">See also</span></span>

- [<span data-ttu-id="7c40a-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7c40a-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="7c40a-115">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7c40a-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
