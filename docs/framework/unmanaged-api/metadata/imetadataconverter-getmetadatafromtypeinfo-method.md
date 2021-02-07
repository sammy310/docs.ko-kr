---
description: '자세히 알아보기: IMetaDataConverter:: GetMetaDataFromTypeInfo 메서드'
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
ms.openlocfilehash: 224be07463b19ed9e22bef1a9d454d91a8086304
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753629"
---
# <a name="imetadataconvertergetmetadatafromtypeinfo-method"></a><span data-ttu-id="312f6-103">IMetaDataConverter::GetMetaDataFromTypeInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="312f6-103">IMetaDataConverter::GetMetaDataFromTypeInfo Method</span></span>

<span data-ttu-id="312f6-104">지정 된 인스턴스가 참조 하는 형식 라이브러리의 메타 데이터 서명을 나타내는 [IMetaDataImport](imetadataimport-interface.md) 인스턴스에 대 한 포인터를 가져옵니다 `ITypeInfo` .</span><span class="sxs-lookup"><span data-stu-id="312f6-104">Gets a pointer to an [IMetaDataImport](imetadataimport-interface.md) instance that represents the metadata signature of the type library referenced by the specified `ITypeInfo` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="312f6-105">구문</span><span class="sxs-lookup"><span data-stu-id="312f6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeInfo (  
    [in]  ITypeInfo         *pITI,  
    [out] IMetaDataImport   **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="312f6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="312f6-106">Parameters</span></span>  

 `pITI`  
 <span data-ttu-id="312f6-107">진행 `ITypeInfo` 형식 라이브러리를 참조 하는 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="312f6-107">[in] A pointer to an `ITypeInfo` object that refers to the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="312f6-108">제한이 메타 데이터 서명을 나타내는 인스턴스의 주소를 받는 위치에 대 한 포인터입니다 `IMetaDataImport` .</span><span class="sxs-lookup"><span data-stu-id="312f6-108">[out] A pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="312f6-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="312f6-109">Requirements</span></span>  

 <span data-ttu-id="312f6-110">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="312f6-110">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="312f6-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="312f6-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="312f6-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="312f6-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="312f6-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="312f6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="312f6-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="312f6-114">See also</span></span>

- [<span data-ttu-id="312f6-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="312f6-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="312f6-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="312f6-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
