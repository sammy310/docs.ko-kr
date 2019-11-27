---
title: IMetaDataConverter::GetMetaDataFromTypeInfo 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetMetaDataFromTypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeInfo
helpviewer_keywords:
- GetMetaDataFromTypeInfo method [.NET Framework metadata]
- IMetaDataConverter::GetMetaDataFromTypeInfo method [.NET Framework metadata]
ms.assetid: d44484bb-23a3-49c3-9e46-69d0d9ab4f0f
topic_type:
- apiref
ms.openlocfilehash: df7be11e8f275824fca658a9604178e7cf28e3ce
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436296"
---
# <a name="imetadataconvertergetmetadatafromtypeinfo-method"></a><span data-ttu-id="c6d7c-102">IMetaDataConverter::GetMetaDataFromTypeInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="c6d7c-102">IMetaDataConverter::GetMetaDataFromTypeInfo Method</span></span>
<span data-ttu-id="c6d7c-103">지정 된 `ITypeInfo` 인스턴스가 참조 하는 형식 라이브러리의 메타 데이터 서명을 나타내는 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-103">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library referenced by the specified `ITypeInfo` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6d7c-104">구문</span><span class="sxs-lookup"><span data-stu-id="c6d7c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeInfo (  
    [in]  ITypeInfo         *pITI,  
    [out] IMetaDataImport   **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6d7c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c6d7c-105">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="c6d7c-106">진행 형식 라이브러리를 참조 하는 `ITypeInfo` 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-106">[in] A pointer to an `ITypeInfo` object that refers to the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="c6d7c-107">제한이 메타 데이터 서명을 나타내는 `IMetaDataImport` 인스턴스의 주소를 수신 하는 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-107">[out] A pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6d7c-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c6d7c-108">Requirements</span></span>  
 <span data-ttu-id="c6d7c-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6d7c-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="c6d7c-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c6d7c-111">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6d7c-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c6d7c-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6d7c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6d7c-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="c6d7c-113">See also</span></span>

- [<span data-ttu-id="c6d7c-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6d7c-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c6d7c-115">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6d7c-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
