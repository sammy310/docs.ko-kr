---
description: '자세히 알아보기: IMetaDataImport2 인터페이스'
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
ms.openlocfilehash: de1b190ae174c6028e4f116d7f6fc0b9af0aac6d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688548"
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="163d5-103">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="163d5-103">IMetaDataImport2 Interface</span></span>

<span data-ttu-id="163d5-104">[IMetaDataImport](imetadataimport-interface.md) 인터페이스를 확장 하 여 제네릭 형식으로 작업 하는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="163d5-104">Extends the [IMetaDataImport](imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="163d5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="163d5-105">Methods</span></span>  
  
|<span data-ttu-id="163d5-106">메서드</span><span class="sxs-lookup"><span data-stu-id="163d5-106">Method</span></span>|<span data-ttu-id="163d5-107">설명</span><span class="sxs-lookup"><span data-stu-id="163d5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="163d5-108">EnumGenericParamConstraints 메서드</span><span class="sxs-lookup"><span data-stu-id="163d5-108">EnumGenericParamConstraints Method</span></span>](imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="163d5-109">지정 된 토큰이 나타내는 제네릭 매개 변수와 연결 된 제네릭 매개 변수 제약 조건의 배열에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="163d5-109">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="163d5-110">EnumGenericParams 메서드</span><span class="sxs-lookup"><span data-stu-id="163d5-110">EnumGenericParams Method</span></span>](imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="163d5-111">지정 된 TypeDef 또는 MethodDef 토큰과 연결 된 제네릭 매개 변수 토큰의 배열에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="163d5-111">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="163d5-112">EnumMethodSpecs 메서드</span><span class="sxs-lookup"><span data-stu-id="163d5-112">EnumMethodSpecs Method</span></span>](imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="163d5-113">지정 된 MethodDef 또는 MemberRef 토큰과 연결 된 MethodSpec 토큰 배열의 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="163d5-113">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="163d5-114">GetGenericParamConstraintProps 메서드</span><span class="sxs-lookup"><span data-stu-id="163d5-114">GetGenericParamConstraintProps Method</span></span>](imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="163d5-115">지정 된 제약 조건 토큰이 나타내는 제네릭 매개 변수 제약 조건과 연결 된 메타 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="163d5-115">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="163d5-116">GetGenericParamProps 메서드</span><span class="sxs-lookup"><span data-stu-id="163d5-116">GetGenericParamProps Method</span></span>](imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="163d5-117">지정 된 토큰이 나타내는 제네릭 매개 변수와 연결 된 메타 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="163d5-117">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="163d5-118">GetMethodSpecProps 메서드</span><span class="sxs-lookup"><span data-stu-id="163d5-118">GetMethodSpecProps Method</span></span>](imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="163d5-119">지정 된 MethodSpec 토큰에서 참조 하는 메서드의 메타 데이터 서명을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="163d5-119">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="163d5-120">GetPEKind 메서드</span><span class="sxs-lookup"><span data-stu-id="163d5-120">GetPEKind Method</span></span>](imetadataimport2-getpekind-method.md)|<span data-ttu-id="163d5-121">현재 메타 데이터 범위에 정의 된 PE (이식 가능한 실행) 파일 (일반적으로 DLL 또는 EXE 파일)에서 코드의 특성을 식별 하는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="163d5-121">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="163d5-122">GetVersionString 메서드</span><span class="sxs-lookup"><span data-stu-id="163d5-122">GetVersionString Method</span></span>](imetadataimport2-getversionstring-method.md)|<span data-ttu-id="163d5-123">어셈블리를 빌드하는 데 사용 된 런타임의 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="163d5-123">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="163d5-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="163d5-124">Requirements</span></span>  

 <span data-ttu-id="163d5-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="163d5-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="163d5-126">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="163d5-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="163d5-127">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="163d5-127">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="163d5-128">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="163d5-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="163d5-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="163d5-129">See also</span></span>

- <xref:System.Reflection.PortableExecutableKinds>
- [<span data-ttu-id="163d5-130">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="163d5-130">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="163d5-131">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="163d5-131">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
