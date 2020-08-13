---
title: ControlBuilderInterceptor 클래스
ms.date: 08/11/2020
api_name:
- System.Web.Compilation.ControlBuilderInterceptor
api_location:
- System.Web.dll
api_type:
- Assembly
topic_type:
- apiref
ms.openlocfilehash: 0cd7409deb9cb84783cfa70600999fa4b2a2d2e2
ms.sourcegitcommit: d337df55f83325918cbbd095eb573400bea49064
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2020
ms.locfileid: "88187989"
---
# <a name="controlbuilderinterceptor-class"></a>ControlBuilderInterceptor 클래스

`ControlBuilderInterceptor`클래스를 사용 하면 컴파일 프로세스를 사용자 지정 하거나 제어할 수 있습니다.

## <a name="syntax"></a>Syntax

```csharp
internal class ControlBuilderInterceptor
```

> [!WARNING]
> `ControlBuilderInterceptor`클래스는 내부 클래스 이며 코드에서 직접 사용할 수 없습니다.
>
> 설명 섹션에 설명 된 대로이 형식의 존재를 확인 하 여 인터셉터 형식 지원이 있는지 여부를 확인할 수 있습니다. Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스의 다른 사용을 지원 하지 않습니다.

## <a name="remarks"></a>설명

.NET Framework 2.0 및 .NET Framework 3.5에서 [8 월 2020](https://portal.msrc.microsoft.com/security-guidance/releasenotedetail/2020-Aug) 업데이트는 인터셉터 형식을 사용 하 여 컴파일 프로세스를 사용자 지정 하거나 제어 하는 지원을 추가 했습니다. <xref:System.Type.GetType?displayProperty=nameWithType> `ControlBuilderInterceptor` 다음 코드에 나와 있는 것 처럼을 사용 하 여 형식이 있는지 확인 하 여이 지원이 있는지 확인할 수 있습니다.

```csharp
Type type = Type.GetType("System.Web.Compilation.ControlBuilderInterceptor, System.Web, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a");
```

반환 값이 null이 아닌 경우 인터셉터 지원이 제공 됩니다. 반환 값이 `null` 이거나 예외가 throw 되 면 8 월 2020 업데이트가 설치 되지 않은 것 이며 인터셉터 지원이 없습니다.

인터셉터 지원이 있는 경우에는 <xref:System.Web.Compilation.ControlBuilderInterceptor> 이후 버전의 .NET Framework와 동일 하 게 동일한 방법으로 컴파일 프로세스와 상호 작용 하는 인터셉터 형식을 작성 하 고 등록할 수 있습니다. .NET Framework 2.0 및 .NET Framework 3.5에서 인터셉터 형식은 다음 요구 사항을 충족 하는 모든 클래스가 될 수 있습니다.

* 에는 매개 변수가 없는 public 생성자가 있습니다.
* 에는 및 `PreControlBuilderInit` 메서드와 동일한 시그니처 및 의미 체계를 가진 및 라는 공용 비정적 메서드가 있으며,이 메서드는 `OnProcessGeneratedCode` <xref:System.Web.Compilation.ControlBuilderInterceptor.PreControlBuilderInit(System.Web.UI.ControlBuilder,System.Web.UI.TemplateParser,System.Web.UI.ControlBuilder,System.Type,System.String,System.String,System.Collections.IDictionary,System.Collections.IDictionary)> <xref:System.Web.Compilation.ControlBuilderInterceptor.OnProcessGeneratedCode(System.Web.UI.ControlBuilder,System.CodeDom.CodeCompileUnit,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeMemberMethod,System.CodeDom.CodeMemberMethod,System.Collections.IDictionary)> 이후 버전의 .NET Framework에 존재 합니다.

`aspnet:20ControlBuilderInterceptor`ASP.NET 응용 프로그램 설정 ()의 키를 사용 하 여 인터셉터 형식을 등록 `<appSettings>` 합니다. 이 응용 프로그램 설정은 컴퓨터 또는 응용 프로그램 *web.config* 파일에 나열 되어야 합니다. 어셈블리의 정규화 된 형식 이름을 사용 하 여 인터셉터 형식을 지정 합니다. 다음 예제에서는 라는 인터셉터 형식을 등록 하는 방법을 보여 줍니다 `Fabrikam.Interceptor` .

```xml
<configuration>
  ...
  <appSettings>
    ...
    <add key="aspnet:20ControlBuilderInterceptor"
         value="Fabrikam.Interceptor, Fabrikam, Version=1.0.0.0, Culture=neutral, PublicKeyToken=2b3831f2f2b744f7" />
  </appSettings>
</configuration>
```

형식의 어셈블리 정규화 된 이름을 검색 하려면 <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType> 다음 코드에 나와 있는 것 처럼 속성을 사용 합니다.

```csharp
string assemblyQualifiedName = typeof(Fabrikam.Interceptor).AssemblyQualifiedName;
```

인터셉터 지원이 있으면 컴파일 프로세스가 위에 설명 된 방식으로 나열 된 형식과 상호 작용 합니다. 인터셉터 지원이 없으면 응용 프로그램 설정이 무시 되 고 적용 되지 않습니다.

## <a name="requirements"></a>요구 사항

**네임 스페이스:** System.web. 컴파일

**어셈블리:** System.web (System.Web.dll)

**.NET Framework 버전:** 3.5, 2.0
