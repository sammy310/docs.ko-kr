---
title: CorNativeType 열거형
ms.date: 03/30/2017
api_name:
- CorNativeType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeType
helpviewer_keywords:
- CorNativeType enumeration [.NET Framework metadata]
ms.assetid: e47a72f1-9609-48ed-bb34-97170d7f6890
topic_type:
- apiref
ms.openlocfilehash: 09a351db65c7ed310d3eb68c71a5207ed6040dd4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177964"
---
# <a name="cornativetype-enumeration"></a>CorNativeType 열거형
관리되지 않는 네이티브 형식을 설명하는 값을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorNativeType {  
  
    NATIVE_TYPE_END                  = 0x0,  
    NATIVE_TYPE_VOID                 = 0x1,  
    NATIVE_TYPE_BOOLEAN              = 0x2,  
    NATIVE_TYPE_I1                   = 0x3,  
    NATIVE_TYPE_U1                   = 0x4,  
    NATIVE_TYPE_I2                   = 0x5,  
    NATIVE_TYPE_U2                   = 0x6,  
    NATIVE_TYPE_I4                   = 0x7,  
    NATIVE_TYPE_U4                   = 0x8,  
    NATIVE_TYPE_I8                   = 0x9,  
    NATIVE_TYPE_U8                   = 0xa,  
    NATIVE_TYPE_R4                   = 0xb,  
    NATIVE_TYPE_R8                   = 0xc,  
    NATIVE_TYPE_SYSCHAR              = 0xd,  
    NATIVE_TYPE_VARIANT              = 0xe,  
    NATIVE_TYPE_CURRENCY             = 0xf,  
    NATIVE_TYPE_PTR                  = 0x10,  
  
    NATIVE_TYPE_DECIMAL              = 0x11,  
    NATIVE_TYPE_DATE                 = 0x12,  
    NATIVE_TYPE_BSTR                 = 0x13,  
    NATIVE_TYPE_LPSTR                = 0x14,  
    NATIVE_TYPE_LPWSTR               = 0x15,  
    NATIVE_TYPE_LPTSTR               = 0x16,  
    NATIVE_TYPE_FIXEDSYSSTRING       = 0x17,  
    NATIVE_TYPE_OBJECTREF            = 0x18,  
    NATIVE_TYPE_IUNKNOWN             = 0x19,  
    NATIVE_TYPE_IDISPATCH            = 0x1a,  
    NATIVE_TYPE_STRUCT               = 0x1b,  
    NATIVE_TYPE_INTF                 = 0x1c,  
    NATIVE_TYPE_SAFEARRAY            = 0x1d,  
    NATIVE_TYPE_FIXEDARRAY           = 0x1e,  
    NATIVE_TYPE_INT                  = 0x1f,  
    NATIVE_TYPE_UINT                 = 0x20,  
  
    NATIVE_TYPE_NESTEDSTRUCT         = 0x21,  
    NATIVE_TYPE_BYVALSTR             = 0x22,  
    NATIVE_TYPE_ANSIBSTR             = 0x23,  
    NATIVE_TYPE_TBSTR                = 0x24,  
    NATIVE_TYPE_VARIANTBOOL          = 0x25,  
    NATIVE_TYPE_FUNC                 = 0x26,  
  
    NATIVE_TYPE_ASANY                = 0x28,  
    NATIVE_TYPE_ARRAY                = 0x2a,  
    NATIVE_TYPE_LPSTRUCT             = 0x2b,  
    NATIVE_TYPE_CUSTOMMARSHALER      = 0x2c,  
    NATIVE_TYPE_IINSPECTABLE         = 0x2e,  
    NATIVE_TYPE_HSTRING              = 0x2f,  
  
    NATIVE_TYPE_ERROR                = 0x2d,
  
    NATIVE_TYPE_MAX                  = 0x50  
  
} CorNativeType;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|Description|  
|------------|-----------------|  
|`NATIVE_TYPE_END`|더 이상 사용되지 않습니다.|  
|`NATIVE_TYPE_VOID`|더 이상 사용되지 않습니다.|  
|`NATIVE_TYPE_BOOLEAN`|TRUE가 0이 아닌 4바이트 부울 값과 FALSE는 0입니다.|  
|`NATIVE_TYPE_I1`|서명된 8비트 정수 값입니다.|  
|`NATIVE_TYPE_U1`|서명되지 않은 8비트 정수 값입니다.|  
|`NATIVE_TYPE_I2`|서명된 16비트 정수 값입니다.|  
|`NATIVE_TYPE_U2`|서명되지 않은 16비트 정수 값입니다.|  
|`NATIVE_TYPE_I4`|부호 있는 32비트 정수 값입니다.|  
|`NATIVE_TYPE_U4`|부호 없는 32비트 정수 값입니다.|  
|`NATIVE_TYPE_I8`|서명된 64비트 정수 값입니다.|  
|`NATIVE_TYPE_U8`|서명되지 않은 64비트 정수 값입니다.|  
|`NATIVE_TYPE_R4`|4바이트 부동 점 숫자 값입니다.|  
|`NATIVE_TYPE_R8`|8바이트 부동 점 숫자 값입니다.|  
|`NATIVE_TYPE_SYSCHAR`|더 이상 사용되지 않습니다.|  
|`NATIVE_TYPE_VARIANT`|더 이상 사용되지 않습니다.|  
|`NATIVE_TYPE_CURRENCY`|관리되는 <xref:System.Decimal> 형식에 해당하는 숫자 COM 형식입니다.|  
|`NATIVE_TYPE_PTR`|더 이상 사용되지 않습니다.|  
|`NATIVE_TYPE_DECIMAL`|더 이상 사용되지 않습니다.|  
|`NATIVE_TYPE_DATE`|더 이상 사용되지 않습니다.|  
|`NATIVE_TYPE_BSTR`|COM Interop를 참조하세요.|  
|`NATIVE_TYPE_LPSTR`|LPSTR 문자열 값입니다.|  
|`NATIVE_TYPE_LPWSTR`|LPWSTR 문자열 값입니다.|  
|`NATIVE_TYPE_LPTSTR`|LPTSTR 문자열 값입니다.|  
|`NATIVE_TYPE_FIXEDSYSSTRING`|고정된 시스템 정의 문자열 값입니다.|  
|`NATIVE_TYPE_OBJECTREF`|더 이상 사용되지 않습니다.|  
|`NATIVE_TYPE_IUNKNOWN`|COM Interop를 참조하세요.|  
|`NATIVE_TYPE_IDISPATCH`|COM Interop를 참조하세요.|  
|`NATIVE_TYPE_STRUCT`|네이티브 구조값입니다.|  
|`NATIVE_TYPE_INTF`|COM Interop를 참조하세요.|  
|`NATIVE_TYPE_SAFEARRAY`|COM Interop를 참조하세요.|  
|`NATIVE_TYPE_FIXEDARRAY`|고정 길이 배열 값입니다.|  
|`NATIVE_TYPE_INT`|네이티브 16비트 서명된 정수 값입니다.|  
|`NATIVE_TYPE_UINT`|서명되지 않은 네이티브 16비트 정수 값입니다.|  
|`NATIVE_TYPE_NESTEDSTRUCT`|더 이상 사용되지 않습니다.<br /><br /> NATIVE_TYPE_STRUCT 사용합니다.|  
|`NATIVE_TYPE_BYVALSTR`|COM Interop를 참조하세요.|  
|`NATIVE_TYPE_ANSIBSTR`|COM Interop를 참조하세요.|  
|`NATIVE_TYPE_TBSTR`|COM Interop를 참조하세요.<br /><br /> 플랫폼에 따라 BSTR 또는 ANSIBSTR을 선택합니다.|  
|`NATIVE_TYPE_VARIANTBOOL`|TRUE가 -1이고 FALSE가 0인 2바이트 부울 값입니다.|  
|`NATIVE_TYPE_FUNC`|함수 포인터입니다.|  
|`NATIVE_TYPE_ASANY`|모든 네이티브 형식에 대한 참조입니다.|  
|`NATIVE_TYPE_ARRAY`|지정되지 않은 형식의 멤버가 있는 배열에 대한 참조입니다.|  
|`NATIVE_TYPE_LPSTRUCT`|구조에 대한 32비트 정수 포인터입니다.|  
|`NATIVE_TYPE_CUSTOMMARSHALER`|사용자 지정 마샬러 네이티브 형식입니다.<br /><br /> "네이티브 형식 이름/0Custom 마샬러 유형 이름/0선택적 쿠키/0" 또는 "{네이티브 형식 GUID}/0사용자 정의 마샬러 유형 이름/0Optional 쿠키/0" 형식의 문자열 이 뒤따라야 합니다.|  
|`NATIVE_TYPE_ERROR`|COM Interop를 참조하세요.<br /><br /> ELEMENT_TYPE_I4 이 유형은 VT_HRESULT 맵을 제공합니다.|  
|`NATIVE_TYPE_IINSPECTABLE`|네이티브 `IInspectable` 형식입니다.|  
|`NATIVE_TYPE_HSTRING`|네이티브 `HString`.|  
|`NATIVE_TYPE_MAX`|잘못된 값입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르Hdr.h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Runtime.InteropServices.UnmanagedType>
- [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
