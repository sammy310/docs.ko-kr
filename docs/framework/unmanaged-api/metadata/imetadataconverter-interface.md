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
ms.openlocfilehash: b771b368c069a4577d266b47bfb4a5ee1935e48e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436264"
---
# <a name="imetadataconverter-interface"></a><span data-ttu-id="825bf-102">IMetaDataConverter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="825bf-102">IMetaDataConverter Interface</span></span>
<span data-ttu-id="825bf-103">형식 라이브러리를 메타데이터 서명에 매핑하고 서로 변환하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="825bf-103">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="825bf-104">메서드</span><span class="sxs-lookup"><span data-stu-id="825bf-104">Methods</span></span>  
  
|<span data-ttu-id="825bf-105">메서드</span><span class="sxs-lookup"><span data-stu-id="825bf-105">Method</span></span>|<span data-ttu-id="825bf-106">설명</span><span class="sxs-lookup"><span data-stu-id="825bf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="825bf-107">GetMetaDataFromTypeInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="825bf-107">GetMetaDataFromTypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypeinfo-method.md)|<span data-ttu-id="825bf-108">지정 된 `ITypeInfo` 인스턴스가 참조 하는 형식 라이브러리에 대 한 메타 데이터 서명을 나타내는 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="825bf-108">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span></span>|  
|[<span data-ttu-id="825bf-109">GetMetaDataFromTypeLib 메서드</span><span class="sxs-lookup"><span data-stu-id="825bf-109">GetMetaDataFromTypeLib Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypelib-method.md)|<span data-ttu-id="825bf-110">지정 된 `ITypeLib` 인스턴스가 나타내는 형식 라이브러리에 대 한 메타 데이터 서명을 나타내는 `IMetaDataImport` 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="825bf-110">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span></span>|  
|[<span data-ttu-id="825bf-111">GetTypeLibFromMetaData 메서드</span><span class="sxs-lookup"><span data-stu-id="825bf-111">GetTypeLibFromMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-gettypelibfrommetadata-method.md)|<span data-ttu-id="825bf-112">지정 된 모듈 및 라이브러리 이름이 있는 형식 라이브러리를 나타내는 `ITypeLib` 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="825bf-112">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="825bf-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="825bf-113">Requirements</span></span>  
 <span data-ttu-id="825bf-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="825bf-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="825bf-115">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="825bf-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="825bf-116">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="825bf-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="825bf-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="825bf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="825bf-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="825bf-118">See also</span></span>

- [<span data-ttu-id="825bf-119">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="825bf-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="825bf-120">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="825bf-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
