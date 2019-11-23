---
title: IMetaDataEmit2 인터페이스
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2
helpviewer_keywords:
- IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type:
- apiref
ms.openlocfilehash: 7ceae6f7713ab0eb1feff550838325df0ea52de2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447922"
---
# <a name="imetadataemit2-interface"></a>IMetaDataEmit2 인터페이스
Extends the [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[DefineGenericParam 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|Creates a definition for a generic type parameter, and gets a token to that generic type parameter.|  
|[DefineMethodSpec 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|Creates a generic instance of a method, and gets a token to the definition.|  
|[GetDeltaSaveSize 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.|  
|[ResetENCLog 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|Resets the edit-and-continue log and starts a new session.|  
|[SaveDelta 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|Saves changes from the current edit-and-continue session to the specified file.|  
|[SaveDeltaToMemory 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|Saves changes from the current edit-and-continue session to memory.|  
|[SaveDeltaToStream 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|Saves changes from the current edit-and-continue session to the specified stream.|  
|[SetGenericParamProps 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|Sets property values for the generic parameter definition referenced by the specified token.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **Header:** Cor.h  
  
 **Library:** Used as a resource in MsCorEE.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [메타데이터 인터페이스](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
