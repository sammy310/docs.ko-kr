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
ms.openlocfilehash: 8f8c0c2cb8dea8ad2b9c0040654122ef5942aca0
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008393"
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a><span data-ttu-id="8e4b3-102">IMetaDataConverter::GetMetaDataFromTypeLib 메서드</span><span class="sxs-lookup"><span data-stu-id="8e4b3-102">IMetaDataConverter::GetMetaDataFromTypeLib Method</span></span>
<span data-ttu-id="8e4b3-103">지정 된 인스턴스가 나타내는 형식 라이브러리의 메타 데이터 서명을 나타내는 [IMetaDataImport](imetadataimport-interface.md) 인스턴스에 대 한 인터페이스 포인터를 가져옵니다 `ITypeLib` .</span><span class="sxs-lookup"><span data-stu-id="8e4b3-103">Gets an interface pointer to an [IMetaDataImport](imetadataimport-interface.md) instance that represents the metadata signature of the type library represented by the specified `ITypeLib` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e4b3-104">구문</span><span class="sxs-lookup"><span data-stu-id="8e4b3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,
    [out] IMetaDataImport **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e4b3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8e4b3-105">Parameters</span></span>  
 `pITL`  
 <span data-ttu-id="8e4b3-106">진행 형식 라이브러리를 나타내는 개체에 대 한 포인터 `ITypeLib` 입니다.</span><span class="sxs-lookup"><span data-stu-id="8e4b3-106">[in] Pointer to an `ITypeLib` object that represents the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="8e4b3-107">제한이 메타 데이터 서명을 나타내는 인스턴스의 주소를 받는 위치에 대 한 포인터입니다 `IMetaDataImport` .</span><span class="sxs-lookup"><span data-stu-id="8e4b3-107">[out] Pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e4b3-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8e4b3-108">Requirements</span></span>  
 <span data-ttu-id="8e4b3-109">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8e4b3-109">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e4b3-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="8e4b3-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8e4b3-111">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e4b3-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8e4b3-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e4b3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e4b3-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e4b3-113">See also</span></span>

- [<span data-ttu-id="8e4b3-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e4b3-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="8e4b3-115">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e4b3-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
