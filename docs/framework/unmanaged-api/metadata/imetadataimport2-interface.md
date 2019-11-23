---
title: IMetaDataImport2 인터페이스
ms.date: 03/30/2017
api_name:
- IMetaDataImport2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2
helpviewer_keywords:
- IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type:
- apiref
ms.openlocfilehash: 0fd7915ef46899bdce8312bc6e8a466167e26382
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429215"
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="f65d8-102">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f65d8-102">IMetaDataImport2 Interface</span></span>
<span data-ttu-id="f65d8-103">Extends the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface to provide the capability of working with generic types.</span><span class="sxs-lookup"><span data-stu-id="f65d8-103">Extends the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f65d8-104">메서드</span><span class="sxs-lookup"><span data-stu-id="f65d8-104">Methods</span></span>  
  
|<span data-ttu-id="f65d8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f65d8-105">Method</span></span>|<span data-ttu-id="f65d8-106">설명</span><span class="sxs-lookup"><span data-stu-id="f65d8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f65d8-107">EnumGenericParamConstraints 메서드</span><span class="sxs-lookup"><span data-stu-id="f65d8-107">EnumGenericParamConstraints Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="f65d8-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span><span class="sxs-lookup"><span data-stu-id="f65d8-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="f65d8-109">EnumGenericParams 메서드</span><span class="sxs-lookup"><span data-stu-id="f65d8-109">EnumGenericParams Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="f65d8-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span><span class="sxs-lookup"><span data-stu-id="f65d8-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="f65d8-111">EnumMethodSpecs 메서드</span><span class="sxs-lookup"><span data-stu-id="f65d8-111">EnumMethodSpecs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="f65d8-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span><span class="sxs-lookup"><span data-stu-id="f65d8-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="f65d8-113">GetGenericParamConstraintProps 메서드</span><span class="sxs-lookup"><span data-stu-id="f65d8-113">GetGenericParamConstraintProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="f65d8-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span><span class="sxs-lookup"><span data-stu-id="f65d8-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="f65d8-115">GetGenericParamProps 메서드</span><span class="sxs-lookup"><span data-stu-id="f65d8-115">GetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="f65d8-116">Gets the metadata associated with the generic parameter represented by the specified token.</span><span class="sxs-lookup"><span data-stu-id="f65d8-116">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="f65d8-117">GetMethodSpecProps 메서드</span><span class="sxs-lookup"><span data-stu-id="f65d8-117">GetMethodSpecProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="f65d8-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span><span class="sxs-lookup"><span data-stu-id="f65d8-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="f65d8-119">GetPEKind 메서드</span><span class="sxs-lookup"><span data-stu-id="f65d8-119">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)|<span data-ttu-id="f65d8-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span><span class="sxs-lookup"><span data-stu-id="f65d8-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="f65d8-121">GetVersionString 메서드</span><span class="sxs-lookup"><span data-stu-id="f65d8-121">GetVersionString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getversionstring-method.md)|<span data-ttu-id="f65d8-122">Gets the version number of the runtime that was used to build the assembly.</span><span class="sxs-lookup"><span data-stu-id="f65d8-122">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f65d8-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f65d8-123">Requirements</span></span>  
 <span data-ttu-id="f65d8-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f65d8-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f65d8-125">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f65d8-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f65d8-126">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f65d8-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f65d8-127">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f65d8-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f65d8-128">참조</span><span class="sxs-lookup"><span data-stu-id="f65d8-128">See also</span></span>

- <xref:System.Reflection.PortableExecutableKinds>
- [<span data-ttu-id="f65d8-129">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f65d8-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="f65d8-130">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f65d8-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
