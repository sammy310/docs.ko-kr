---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d3377617ddd6b82ad88d22f6ffda04b1d6ae837
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096126"
---
# <a name="imetadataconverter-interface"></a><span data-ttu-id="d41e5-102">IMetaDataConverter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d41e5-102">IMetaDataConverter Interface</span></span>
<span data-ttu-id="d41e5-103">형식 라이브러리를 메타데이터 서명에 매핑하고 서로 변환하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d41e5-103">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d41e5-104">메서드</span><span class="sxs-lookup"><span data-stu-id="d41e5-104">Methods</span></span>  
  
|<span data-ttu-id="d41e5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d41e5-105">Method</span></span>|<span data-ttu-id="d41e5-106">설명</span><span class="sxs-lookup"><span data-stu-id="d41e5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d41e5-107">GetMetaDataFromTypeInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="d41e5-107">GetMetaDataFromTypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypeinfo-method.md)|<span data-ttu-id="d41e5-108">포인터를 가져는 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 지정 된 참조 형식 라이브러리에 대 한 메타 데이터 시그니처를 나타내는 인스턴스 `ITypeInfo` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="d41e5-108">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span></span>|  
|[<span data-ttu-id="d41e5-109">GetMetaDataFromTypeLib 메서드</span><span class="sxs-lookup"><span data-stu-id="d41e5-109">GetMetaDataFromTypeLib Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypelib-method.md)|<span data-ttu-id="d41e5-110">포인터를 가져는 `IMetaDataImport` 지정 된 형식 라이브러리에 대 한 메타 데이터 시그니처를 나타내는 인스턴스 `ITypeLib` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="d41e5-110">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span></span>|  
|[<span data-ttu-id="d41e5-111">GetTypeLibFromMetaData 메서드</span><span class="sxs-lookup"><span data-stu-id="d41e5-111">GetTypeLibFromMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-gettypelibfrommetadata-method.md)|<span data-ttu-id="d41e5-112">포인터를 가져는 `ITypeLib` 지정 된 모듈 및 라이브러리 이름에는 형식 라이브러리를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="d41e5-112">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d41e5-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d41e5-113">Requirements</span></span>  
 <span data-ttu-id="d41e5-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d41e5-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d41e5-115">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d41e5-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d41e5-116">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="d41e5-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="d41e5-117">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="d41e5-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d41e5-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="d41e5-118">See also</span></span>

- [<span data-ttu-id="d41e5-119">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d41e5-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="d41e5-120">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d41e5-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
