---
description: '자세히 알아보기: IMetaDataConverter 인터페이스'
title: IMetaDataConverter 인터페이스
ms.date: 03/30/2017
api_name:
- IMetaDataConverter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter
helpviewer_keywords:
- IMetaDataConverter interface [.NET Framework metadata]
ms.assetid: 9caea662-0167-4267-b14a-2fa42c3be4ea
topic_type:
- apiref
ms.openlocfilehash: 6ed84083bad924e760c576afe485bd7ccad012cf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789257"
---
# <a name="imetadataconverter-interface"></a><span data-ttu-id="3c651-103">IMetaDataConverter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3c651-103">IMetaDataConverter Interface</span></span>

<span data-ttu-id="3c651-104">형식 라이브러리를 메타데이터 서명에 매핑하고 서로 변환하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3c651-104">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3c651-105">메서드</span><span class="sxs-lookup"><span data-stu-id="3c651-105">Methods</span></span>  
  
|<span data-ttu-id="3c651-106">메서드</span><span class="sxs-lookup"><span data-stu-id="3c651-106">Method</span></span>|<span data-ttu-id="3c651-107">설명</span><span class="sxs-lookup"><span data-stu-id="3c651-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3c651-108">GetMetaDataFromTypeInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="3c651-108">GetMetaDataFromTypeInfo Method</span></span>](imetadataconverter-getmetadatafromtypeinfo-method.md)|<span data-ttu-id="3c651-109">지정 된 인스턴스가 참조 하는 형식 라이브러리에 대 한 메타 데이터 서명을 나타내는 [IMetaDataImport](imetadataimport-interface.md) 인스턴스에 대 한 포인터를 가져옵니다 `ITypeInfo` .</span><span class="sxs-lookup"><span data-stu-id="3c651-109">Gets a pointer to an [IMetaDataImport](imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span></span>|  
|[<span data-ttu-id="3c651-110">GetMetaDataFromTypeLib 메서드</span><span class="sxs-lookup"><span data-stu-id="3c651-110">GetMetaDataFromTypeLib Method</span></span>](imetadataconverter-getmetadatafromtypelib-method.md)|<span data-ttu-id="3c651-111">`IMetaDataImport`지정 된 인스턴스가 나타내는 형식 라이브러리에 대 한 메타 데이터 서명을 나타내는 인스턴스에 대 한 포인터를 가져옵니다 `ITypeLib` .</span><span class="sxs-lookup"><span data-stu-id="3c651-111">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span></span>|  
|[<span data-ttu-id="3c651-112">GetTypeLibFromMetaData 메서드</span><span class="sxs-lookup"><span data-stu-id="3c651-112">GetTypeLibFromMetaData Method</span></span>](imetadataconverter-gettypelibfrommetadata-method.md)|<span data-ttu-id="3c651-113">`ITypeLib`지정 된 모듈 및 라이브러리 이름이 있는 형식 라이브러리를 나타내는 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3c651-113">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3c651-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3c651-114">Requirements</span></span>  

 <span data-ttu-id="3c651-115">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3c651-115">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c651-116">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="3c651-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3c651-117">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c651-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3c651-118">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c651-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c651-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c651-119">See also</span></span>

- [<span data-ttu-id="3c651-120">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3c651-120">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="3c651-121">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3c651-121">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
