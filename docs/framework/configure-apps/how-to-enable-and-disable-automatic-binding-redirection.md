---
title: 자동 생성 된 바인딩 리디렉션을 사용 하지 않도록 설정 하거나 사용
ms.date: 10/30/2018
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 5fca42f3-bdce-4b81-a704-61e42c89d3ba
ms.openlocfilehash: b6c9c3508c53e8a68a3f7e1cb12b6b6c95600e7b
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380096"
---
# <a name="how-to-enable-and-disable-automatic-binding-redirection"></a>방법: 자동 바인딩 리디렉션 사용 설정 및 해제

Visual Studio는 대상.NET Framework 4.5.1 이상 버전에서 앱을 컴파일할 때 어셈블리 통합을 재정의 하려면 앱 구성 파일에 바인딩 리디렉션을 자동으로 추가할 수 있습니다. 수동으로 바인딩 리디렉션을 응용 프로그램의 구성 파일에 지정할 지라도 응용 프로그램 또는 해당 구성 요소가 동일 어셈블리의 두 개 이상의 버전을 참조할 경우 바인딩 리디렉션을 추가합니다. 자동 바인딩 리디렉션 기능 또는 영향을 데스크톱 앱 및 웹 앱 대상인.NET Framework 4.5.1 이상 버전을 웹 앱에 대 한 동작을 약간 다릅니다. 하지만 합니다. 수동으로 바인딩 리디렉션을 작성 하려는 경우에이 기능을 비활성화할 수 있습니다 또는 기존 앱 해당 이전 버전의 대상으로.NET Framework를 있는 경우 자동 바인딩 리디렉션을 사용할 수 있습니다.

## <a name="disable-automatic-binding-redirects-in-desktop-apps"></a>데스크톱 앱에서 자동 바인딩 리디렉션을 사용 하지 않도록 설정

자동 바인딩 리디렉션은 고.NET Framework 4.5.1 이상 버전을 대상으로 하는 Windows 데스크톱 앱에 대해 기본적으로 활성화 됩니다. 바인딩 리디렉션이 출력 구성에 추가 됩니다 (**app.config**) 앱을 컴파일하면 파일과 그렇지 않은 경우에 발생할 수 있는 어셈블리 통합을 재정의 합니다. 소스 **app.config** 파일은 수정 되지 않습니다. 앱 용 프로젝트 파일을 수정 하 여 또는 Visual Studio에서 프로젝트의 속성에 있는 확인란을 선택 취소 하 여이 기능을 비활성화할 수 있습니다.

### <a name="disable-through-project-properties"></a>프로젝트 속성을 통해 사용 하지 않도록 설정

Visual Studio 2017 버전 15.7 이상의 경우 프로젝트의 속성 페이지에서 자동으로 생성 된 바인딩 리디렉션을 쉽게 해제할 수 있습니다.

1. **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.

2. 에 **응용 프로그램** 페이지에서 선택 취소 합니다 **자동 생성 바인딩 리디렉션을** 옵션입니다.

3. 키를 눌러 **Ctrl**+**S** 변경 내용을 저장 합니다.

### <a name="disable-manually-in-the-project-file"></a>프로젝트 파일에서 수동으로 사용 하지 않도록 설정

1. 다음 방법 중 하나를 사용 하 여 편집할 프로젝트 파일을 엽니다.

   - Visual Studio에서 프로젝트를 선택 **솔루션 탐색기**를 선택한 후 **파일 탐색기에서 폴더 열기** 바로 가기 메뉴에서. 파일 탐색기에서 프로젝트 (.csproj 또는.vbproj) 파일을 찾아서 메모장에서 엽니다.
   - Visual Studio에서의 **솔루션 탐색기**프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **프로젝트 언로드**합니다. 언로드된 프로젝트를 다시 마우스 오른쪽 단추로 클릭 하 고 선택한 **[projectname.csproj] 편집**합니다.

2. 프로젝트 파일에서 다음 속성 항목을 찾습니다.

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

3. `true`를 `false`로 변경합니다.

   ```xml
   <AutoGenerateBindingRedirects>false</AutoGenerateBindingRedirects>
   ```

## <a name="enable-automatic-binding-redirects-manually"></a>수동으로 자동 바인딩 리디렉션을 사용 하도록 설정

해당 대상 이전 버전의.NET Framework 또는 자동으로 묻는 리디렉션을 추가 하는 경우 기존 앱에서 자동 바인딩 리디렉션을 사용할 수 있습니다. 최신 버전의 framework 대상으로 하지만 경우 수행 메시지가 자동으로 나타나지 리디렉션을 추가 하 가능성이 어셈블리를 다시 매핑하도록 제안 하는 빌드 출력을 얻게 됩니다.

1. 다음 방법 중 하나를 사용 하 여 편집할 프로젝트 파일을 엽니다.

   - Visual Studio에서 프로젝트를 선택 **솔루션 탐색기**를 선택한 후 **파일 탐색기에서 폴더 열기** 바로 가기 메뉴에서. 파일 탐색기에서 프로젝트 (.csproj 또는.vbproj) 파일을 찾아서 메모장에서 엽니다.
   - Visual Studio에서의 **솔루션 탐색기**프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **프로젝트 언로드**합니다. 언로드된 프로젝트를 다시 마우스 오른쪽 단추로 클릭 하 고 선택한 **[projectname.csproj] 편집**합니다.

2. 첫 번째 구성 속성 그룹에 다음 요소를 추가 (아래는 \<PropertyGroup > 태그).

   ```xml
   <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
   ```

   다음은 삽입 된 요소를 사용 하 여 예제 프로젝트 파일.

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <Project ToolsVersion="12.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
     <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" Condition="Exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props')" />
       <PropertyGroup>
         <Configuration Condition=" '$(Configuration)' == ''     ">Debug</Configuration>
         <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>
         <ProjectGuid>{123334}</ProjectGuid>
         ...
         <AutoGenerateBindingRedirects>true</AutoGenerateBindingRedirects>
       </PropertyGroup>
     ...
   </Project>
   ```

3. 응용 프로그램을 컴파일합니다.

## <a name="enable-automatic-binding-redirects-in-web-apps"></a>Web apps에서 자동 바인딩 리디렉션을 사용 하도록 설정

자동 바인딩 리디렉션은 웹 응용 프로그램마다 다르게 구현됩니다. 때문에 원본 구성 (**web.config**) 웹 앱에 대 한 파일을 수정 해야, 바인딩 리디렉션을 추가 되지 않습니다 자동으로 구성 파일에 있습니다. 하지만 Visual Studio는 바인딩 충돌을 경고하고 충돌 해결을 위해 바인딩 리디렉션을 추가할 수 있습니다. 항상 바인딩 리디렉션을 추가 하는 메시지가 때문에 명시적으로 웹 앱에 대해이 기능을 사용 하지 않도록 설정할 필요가 없습니다.

바인딩 리디렉션을 추가 하는 **web.config** 파일:

1. Visual Studio에서 응용 프로그램을 컴파일하고 빌드 경고를 확인합니다.

   ![어셈블리 참고 충돌에 대 한 경고를 빌드](../../../docs/framework/configure-apps/media/clr-assemblyrefwarning.png "CLR_AssemblyRefWarning")

2. 어셈블리 바인딩 충돌이 있을 경우 경고가 나타납니다. 경고를 두 번 클릭 하거나 선택 하 고 경고 press **Enter**합니다.

   필요한 바인딩을 자동으로 추가할 수 있는 대화 상자를 원본 리디렉션됩니다 **web.config** 파일이 표시 됩니다.

   ![바인딩 리디렉션 권한 대화 상자](../../../docs/framework/configure-apps/media/clr-addbindingredirect.png "CLR_AddBindingRedirect")

## <a name="see-also"></a>참고자료

- [\<bindingRedirect > 요소](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)
- [어셈블리 버전 리디렉션](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
