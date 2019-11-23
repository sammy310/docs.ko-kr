---
title: ICeeGen 인터페이스
ms.date: 03/30/2017
api_name:
- ICeeGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen
helpviewer_keywords:
- ICeeGen interface [.NET Framework metadata]
ms.assetid: 383d20b0-efe9-4e71-8fb8-1186b2e7d0c0
topic_type:
- apiref
ms.openlocfilehash: ae3c372951de00b097d0a8437039a3a85bf3aabf
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426158"
---
# <a name="iceegen-interface"></a>ICeeGen 인터페이스
동적 코드 컴파일에 대한 메서드를 제공합니다.  
  
 This interface is obsolete and should not be used.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[AddSectionReloc 메서드](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)|사용되지 않습니다. Adds a .reloc instruction to the code base.|  
|[AllocateMethodBuffer 메서드](../../../../docs/framework/unmanaged-api/metadata/iceegen-allocatemethodbuffer-method.md)|사용되지 않습니다. Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.|  
|[ComputePointer 메서드](../../../../docs/framework/unmanaged-api/metadata/iceegen-computepointer-method.md)|사용되지 않습니다. Determines the buffer for the specified code section.|  
|[EmitString 메서드](../../../../docs/framework/unmanaged-api/metadata/iceegen-emitstring-method.md)|사용되지 않습니다. Emits the specified string into the code base.|  
|[GenerateCeeFile 메서드](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceefile-method.md)|사용되지 않습니다. Generates a code-base file that contains the code base currently loaded into this `ICeeGen`.|  
|[GenerateCeeMemoryImage 메서드](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceememoryimage-method.md)|사용되지 않습니다. Generates an image in memory for the code base.|  
|[GetIlSection 메서드](../../../../docs/framework/unmanaged-api/metadata/iceegen-getilsection-method.md)|사용되지 않습니다. Gets the section of the intermediate language code base referenced by the specified handle.|  
|[GetIMapTokenIface 메서드](../../../../docs/framework/unmanaged-api/metadata/iceegen-getimaptokeniface-method.md)|사용되지 않습니다. Gets the interface referenced by the specified token.|  
|[GetMethodBuffer 메서드](../../../../docs/framework/unmanaged-api/metadata/iceegen-getmethodbuffer-method.md)|사용되지 않습니다. Gets a buffer of the appropriate size for the method at the specified relative virtual address.|  
|[GetSectionBlock 메서드](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectionblock-method.md)|사용되지 않습니다. Gets a section block of the code base.|  
|[GetSectionCreate 메서드](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectioncreate-method.md)|사용되지 않습니다. Generates and gets a code section using the specified name and flag values.|  
|[GetSectionDataLen 메서드](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectiondatalen-method.md)|사용되지 않습니다. Gets the length of the specified section.|  
|[GetString 메서드](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstring-method.md)|사용되지 않습니다. Gets the string stored at the specified relative virtual address.|  
|[GetStringSection 메서드](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstringsection-method.md)|사용되지 않습니다. Gets a string representation of the code section referenced by the specified handle.|  
|[TruncateSection 메서드](../../../../docs/framework/unmanaged-api/metadata/iceegen-truncatesection-method.md)|사용되지 않습니다. Truncates the specified code section by the specified length.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **Header:** Cor.h  
  
 **Library:** Used as a resource in MsCorEE.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [메타데이터 인터페이스](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
