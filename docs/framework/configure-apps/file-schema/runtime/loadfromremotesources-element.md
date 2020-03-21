---
title: <loadFromRemoteSources> 요소
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
ms.openlocfilehash: a0dcffe378cdd09de0fbd8f0a6ef0635c033fd9c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154064"
---
# <a name="loadfromremotesources-element"></a>\<로드From원격 소스> 요소
.NET Framework 4 이상에서 원격 소스에서 로드된 어셈블리에 대한 완전 신뢰를 부여할지 여부를 지정합니다.
  
> [!NOTE]
> Visual Studio 프로젝트 오류 목록의 오류 메시지 또는 빌드 오류로 인해 이 문서로 이동한 경우 [Visual Studio에서 웹에서 어셈블리 사용 방법을 참조하세요.](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100))  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<런타임>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<로드로부터원격소스>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<loadFromRemoteSources
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 원격 원본에서 로드된 어셈블리에 완전 신뢰가 부여되는지 여부를 지정합니다.|  
  
## <a name="enabled-attribute"></a>활성화된 특성  
  
|값|Description|  
|-----------|-----------------|  
|`false`|원격 소스의 응용 프로그램에 대한 완전 신뢰를 부여하지 마십시오. 이것이 기본값입니다.|  
|`true`|원격 소스의 응용 프로그램에 대한 완전 신뢰를 부여합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명

.NET Framework 3.5 및 이전 버전에서 원격 위치에서 어셈블리를 로드하는 경우 어셈블리의 코드는 로드되는 영역에 종속된 권한 부여 집합을 사용하여 부분 신뢰에서 실행됩니다. 예를 들어 웹 사이트에서 어셈블리를 로드하는 경우 인터넷 영역에 로드되고 인터넷 권한 집합이 부여됩니다. 즉, 인터넷 샌드박스에서 실행됩니다.

.NET Framework 4부터 코드 액세스 보안(CAS) 정책이 비활성화되고 어셈블리가 완전히 신뢰할 수 있습니다. 일반적으로 이렇게 하면 이전에 샌드박스에 있던 <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> 메서드가 로드된 어셈블리에 대한 완전한 신뢰가 부여됩니다. 이를 방지하기 위해 원격 소스에서 로드된 어셈블리에서 코드를 실행하는 기능은 기본적으로 비활성화됩니다. 기본적으로 원격 어셈블리를 로드하려고 하면 <xref:System.IO.FileLoadException> 다음과 같은 예외 메시지가 있는 a가 throw됩니다.

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported.
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' --->
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default,
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch.
```

어셈블리를 로드하고 해당 코드를 실행하려면 다음 중 하나를 수행해야 합니다.

- 어셈블리에 대한 샌드박스를 명시적으로 [만듭니다(샌드박스에서 부분적으로 신뢰할 수 있는 코드를 실행하는 방법 참조).](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)

- 어셈블리의 코드를 완전히 신뢰하여 실행합니다. 요소를 구성하여 이 작업을 `<loadFromRemoteSources>` 수행합니다. 이제 .NET Framework의 이전 버전에서 부분 신뢰로 실행되는 어셈블리가 .NET Framework 4 및 이후 버전에서 완전 신뢰로 실행되도록 지정할 수 있습니다.

> [!IMPORTANT]
> 어셈블리가 완전 신뢰로 실행되지 않아야 하는 경우 이 구성 요소를 설정하지 마십시오. 대신 어셈블리를 로드할 샌드박스를 <xref:System.AppDomain> 만듭니다.

요소에 대한 특성은 `enabled` CAS(코드 액세스 보안)를 사용하지 않도록 설정한 경우에만 유효합니다. `<loadFromRemoteSources>` 기본적으로 CAS 정책은 .NET Framework 4 및 이후 버전에서 비활성화됩니다. 을 `enabled` 설정하면 `true`원격 어셈블리에 완전 신뢰가 부여됩니다.

을 설정하지 않으면 `enabled` <xref:System.IO.FileLoadException> a가 다음 조건 중 하나에서 throw됩니다. `true`

- 현재 도메인의 샌드박싱 동작은 .NET Framework 3.5의 동작과 다릅니다. 이렇게 하려면 CAS 정책을 사용하지 않도록 설정해야 하며 현재 도메인은 샌드박스되지 않습니다.

- 로드되는 어셈블리가 `MyComputer` 영역에서 온 어셈블리가 아닙니다.

`<loadFromRemoteSources>` 요소를 설정하면 `true` 이 예외가 throw되지 않습니다. 이를 통해 공통 언어 런타임에 의존하지 않고 로드된 어셈블리를 보안을 위해 샌드박스에 의존하지 않도록 지정할 수 있으며 완전 신뢰에서 실행할 수 있도록 허용할 수 있습니다.

## <a name="notes"></a>메모

- .NET Framework 4.5 및 이후 버전에서는 로컬 네트워크 공유의 어셈블리가 기본적으로 완전 신뢰로 실행됩니다. `<loadFromRemoteSources>` 요소를 활성화할 필요가 없습니다.

- 애플리케이션을 웹에서 복사한 경우, Windows에서는 해당 프로그램이 로컬 컴퓨터에 있더라도 웹 애플리케이션이라는 플래그가 지정됩니다. 파일 속성을 변경하여 해당 지정을 변경하거나 `<loadFromRemoteSources>` 요소를 사용하여 어셈블리에 전체 신뢰를 부여할 수 있습니다. 또는 <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> 메서드를 사용하여 운영 체제가 웹에서 로드되었음을 표시하는 로컬 어셈블리를 로드할 수 있습니다.

- Windows 가상 <xref:System.IO.FileLoadException> PC 응용 프로그램에서 실행 중인 응용 프로그램에서 를 얻을 수 있습니다. 이 문제는 호스팅 컴퓨터에서 연결된 폴더에서 파일을 로드하려고 할 때 발생할 수 있습니다. [원격 데스크톱 서비스(터미널 서비스)를](/windows/win32/termserv/terminal-services-portal) 통해 연결된 폴더에서 파일을 로드하려고 할 때도 발생할 수 있습니다. 예외를 방지하려면 `enabled` 을 `true`설정합니다.

## <a name="configuration-file"></a>구성 파일

이 요소는 일반적으로 애플리케이션 구성 파일에서 사용하지만 컨텍스트에 따라 다른 구성 파일에서도 사용할 수 있습니다. 자세한 내용은 CAS 정책의 암시적 사용 문서: .NET 보안 블로그의 [loadFromRemoteSource](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) 문서를 참조하십시오.  

## <a name="example"></a>예제

다음 예제에서는 원격 원본에서 로드된 어셈블리에 완전 신뢰를 부여하는 방법을 보여 주습니다.

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a>참고 항목

- [CAS 정책의 더 암시적 사용: 로드로부터원격 소스](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)
- [방법: 샌드박스에서 부분적으로 신뢰할 수 있는 코드 실행](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [런타임 설정 스키마](index.md)
- [구성 파일 스키마](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
