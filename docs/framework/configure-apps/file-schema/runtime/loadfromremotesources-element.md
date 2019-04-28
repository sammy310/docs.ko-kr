---
title: <loadFromRemoteSources> 요소
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7568129f30267b212737ec8aa688cf882e19bbff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704598"
---
# <a name="loadfromremotesources-element"></a>\<loadFromRemoteSources > 요소
지정 여부를 원격 원본에서 로드 된 어셈블리의.NET Framework 4 이상 완전 신뢰를 부여 해야 합니다.
  
> [!NOTE]
>  이 문서에서는 Visual Studio 프로젝트 오류 목록 또는 빌드 오류가 오류 메시지로 인해 연결 된, 참조 [방법: 웹에서 어셈블리를 사용 하 여 Visual Studio에서](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100))합니다.  
  
 \<configuration>  
\<runtime>  
\<loadFromRemoteSources>  
  
## <a name="syntax"></a>구문  
  
```xml  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 지정 여부를 원격 원본에서 로드 된 어셈블리가 완전 신뢰를 부여 해야 합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|원격 원본에서 응용 프로그램에 완전 신뢰를 부여 하지 마세요. 이 값이 기본값입니다.|  
|`true`|원격 원본에서 응용 프로그램에 완전 신뢰를 부여 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명

.NET Framework 3.5 및 이전 버전에서 원격 위치에서 어셈블리를 로드 하는 경우 어셈블리의 코드는이 로드 되는 영역에 따라 달라 지는 권한 부여 집합을 사용 하 여 부분 신뢰에서 실행 됩니다. 예를 들어, 웹 사이트에서 어셈블리를 로드 하는 경우 인터넷 영역으로 로드 하며 인터넷 권한 집합이 부여. 즉, 인터넷 샌드박스에서 실행 됩니다.

.NET Framework 4 부터는 코드 액세스 보안 (CA) 정책 비활성화 되 하 고 어셈블리는 완전 신뢰 수준에서 로드 됩니다. 일반적으로 사용 하 여 로드 된 어셈블리에 완전 신뢰를 부여는이 <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> 있었던 이전에 샌드박스가 적용 된 메서드. 이 방지 하려면 원격 원본에서 로드 된 어셈블리에서 코드를 실행할 수는 기본적으로 비활성화 됩니다. 원격 어셈블리를 로드 하려고 하면 기본적으로는 <xref:System.IO.FileLoadException> 다음이 throw와 같은 예외 메시지:

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported. 
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' ---> 
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly 
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default, 
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch. 
```

에 어셈블리를 로드 하 고 해당 코드를 실행 하거나 다음을 수행 해야 합니다.

- 어셈블리에 대 한 샌드박스를 명시적으로 만들거나 (참조 [방법: 샌드박스에서 부분적으로 신뢰할 수 있는 코드 실행](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).

- 완전 신뢰에서 어셈블리의 코드를 실행 합니다. 구성 하 여이 작업을 수행 합니다 `<loadFromRemoteSources>` 요소입니다. 이전 버전의.NET Framework에서 부분 신뢰로 실행 되는 어셈블리의.NET Framework 4 및 이후 버전에서 완전 신뢰에서 이제 실행 되도록 지정할 수 있습니다.

> [!IMPORTANT]
> 어셈블리를 완전 신뢰로 실행 하지 않아야, 경우에이 구성 요소를 설정 하지 마십시오. 대신 샌드박스를 만들 <xref:System.AppDomain> 는 어셈블리를 로드 합니다.

합니다 `enabled` 특성을 `<loadFromRemoteSources>` 요소 (CA) 코드 액세스 보안을 해제 하는 경우에 적용 됩니다. 기본적으로 CAS 정책은.NET Framework 4 및 이후 버전에서 비활성화 되었습니다. 설정 하는 경우 `enabled` 에 `true`, 원격 어셈블리에 완전 신뢰가 부여 됩니다.

하는 경우 `enabled` 로 설정 되어 있지 `true`, <xref:System.IO.FileLoadException> 다음 조건 중 하나가 throw 됩니다.

- 현재 도메인의 샌드 박싱 동작은.NET Framework 3.5에서의 동작과에서 다릅니다. 샌드 박싱 할 필요가 현재 도메인과 CAS 정책을 사용 하지 않도록 설정할 필요 합니다.

- 로드 되는 어셈블리에서 아닙니다는 `MyComputer` 영역입니다.

설정 된 `<loadFromRemoteSources>` 요소를 `true` 이 예외가 throw 되지 않도록 합니다. 하면 의존 하지 않고 샌드박스에 공용 언어 런타임 보안을 위해 로드 된 어셈블리를 지정할 수 있습니다 및에서 실행 하도록 허용 될 완전 신뢰 합니다.

## <a name="notes"></a>노트

- .NET Framework 4.5 및 이후 버전에서 로컬 네트워크 공유에 어셈블리가 완전 신뢰로 실행 기본적으로 사용 하도록 설정 해야 합니다 `<loadFromRemoteSources>` 요소입니다.

- 응용 프로그램을 웹에서 복사한 경우, Windows에서는 해당 프로그램이 로컬 컴퓨터에 있더라도 웹 응용 프로그램이라는 플래그가 지정됩니다. 파일 속성을 변경 하 여 해당 명칭을 변경할 수 있습니다 또는 사용할 수는 `<loadFromRemoteSources>` 완전 신뢰 어셈블리에 부여할 요소입니다. 또는 <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> 메서드를 사용하여 운영 체제가 웹에서 로드되었음을 표시하는 로컬 어셈블리를 로드할 수 있습니다.

- 표시 될 수 있습니다는 <xref:System.IO.FileLoadException> Windows Virtual PC 응용 프로그램을 실행 하는 응용 프로그램에서 합니다. 이 호스팅 컴퓨터에서 연결 된 폴더에서 파일을 로드 하려고 할 때 발생할 수 있습니다. 또한 통해 연결 된 폴더에서 파일을 로드 하려고 할 때 발생할 수 있습니다 [원격 데스크톱 서비스](https://go.microsoft.com/fwlink/?LinkId=182775) (터미널 서비스). 예외를 방지 하려면 설정 `enabled` 에 `true`입니다.

## <a name="configuration-file"></a>구성 파일

이 요소는 일반적으로 응용 프로그램 구성 파일에서 사용하지만 컨텍스트에 따라 다른 구성 파일에서도 사용할 수 있습니다. 자세한 내용은 문서 참조 [자세한 암시적 사용 하 여 CA 정책: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839) .NET Security 블로그의 합니다.  

## <a name="example"></a>예제

다음 예에서는 원격 원본에서 로드 된 어셈블리에 완전 신뢰를 부여 하는 방법을 보여 줍니다.

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a>참고 항목

- [CAS 정책의 암시적 사용: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839)
- [방법: 샌드박스에서 부분적으로 신뢰할 수 있는 코드 실행](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
