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
ms.openlocfilehash: 1f45310bc65bc8614033182a81db451b79bcf97f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714720"
---
# <a name="imetadataconvertergetmetadatafromtypeinfo-method"></a><span data-ttu-id="48519-102">IMetaDataConverter::GetMetaDataFromTypeInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="48519-102">IMetaDataConverter::GetMetaDataFromTypeInfo Method</span></span>

<span data-ttu-id="48519-103">지정 된 인스턴스가 참조 하는 형식 라이브러리의 메타 데이터 서명을 나타내는 [IMetaDataImport](imetadataimport-interface.md) 인스턴스에 대 한 포인터를 가져옵니다 `ITypeInfo` .</span><span class="sxs-lookup"><span data-stu-id="48519-103">Gets a pointer to an [IMetaDataImport](imetadataimport-interface.md) instance that represents the metadata signature of the type library referenced by the specified `ITypeInfo` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48519-104">구문</span><span class="sxs-lookup"><span data-stu-id="48519-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeInfo (  
    [in]  ITypeInfo         *pITI,  
    [out] IMetaDataImport   **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48519-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="48519-105">Parameters</span></span>  

 `pITI`  
 <span data-ttu-id="48519-106">진행 `ITypeInfo` 형식 라이브러리를 참조 하는 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="48519-106">[in] A pointer to an `ITypeInfo` object that refers to the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="48519-107">제한이 메타 데이터 서명을 나타내는 인스턴스의 주소를 받는 위치에 대 한 포인터입니다 `IMetaDataImport` .</span><span class="sxs-lookup"><span data-stu-id="48519-107">[out] A pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48519-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="48519-108">Requirements</span></span>  

 <span data-ttu-id="48519-109">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48519-109">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48519-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="48519-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="48519-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48519-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="48519-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48519-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48519-113">참조</span><span class="sxs-lookup"><span data-stu-id="48519-113">See also</span></span>

- [<span data-ttu-id="48519-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="48519-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="48519-115">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="48519-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
