---
title: 사용자 지정 My 확장 패키징 및 배포
ms.date: 08/14/2018
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
ms.openlocfilehash: a2e2a6705fb3d8d4424d46d96bbf49b41e1414af
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330254"
---
# <a name="package-and-deploy-custom-my-extensions-visual-basic"></a>사용자 지정 My 확장 패키징 및 배포 (Visual Basic)

Visual Basic Visual Studio 템플릿을 사용 하 여 사용자 지정 `My` 네임 스페이스 확장을 쉽게 배포할 수 있는 방법을 제공 합니다. `My` 확장이 새 프로젝트 형식의 정수 부분인 프로젝트 템플릿을 만드는 경우 템플릿을 내보낼 때 프로젝트에 사용자 지정 `My` 확장 코드를 포함할 수 있습니다. 프로젝트 템플릿 내보내기에 대 한 자세한 내용은 [방법: 프로젝트 템플릿 만들기](/visualstudio/ide/how-to-create-project-templates)를 참조 하세요.

사용자 지정 `My` 확장이 단일 코드 파일에 있는 경우 사용자가 Visual Basic 프로젝트의 모든 형식에 추가할 수 있는 항목 템플릿으로 파일을 내보낼 수 있습니다. 그런 다음 Visual Basic 프로젝트에서 사용자 지정 `My` 확장에 대 한 추가 기능 및 동작을 사용 하도록 항목 템플릿을 사용자 지정할 수 있습니다. 이러한 기능에는 다음이 포함 됩니다.

- 사용자가 Visual Basic 프로젝트 디자이너의 **내 확장** 페이지에서 사용자 지정 `My` 확장을 관리할 수 있도록 허용 합니다.

- 지정 된 어셈블리에 대 한 참조가 프로젝트에 추가 될 때 사용자 지정 `My` 확장을 자동으로 추가 합니다.

- 프로젝트 항목 목록에 포함 되지 않도록 **항목 추가** 대화 상자에서 `My` 확장 항목 템플릿을 숨깁니다.

이 항목에서는 Visual Basic 프로젝트 디자이너의 **내 확장** 페이지에서 관리할 수 있는 숨겨진 항목 템플릿으로 사용자 지정 `My` 확장을 패키징하는 방법에 대해 설명 합니다. 지정 된 어셈블리에 대 한 참조가 프로젝트에 추가 될 때 사용자 지정 `My` 확장을 자동으로 추가할 수도 있습니다.

## <a name="create-a-my-namespace-extension"></a>My 네임 스페이스 확장 만들기

사용자 지정 `My` 확장에 대 한 배포 패키지를 만드는 첫 번째 단계는 확장을 단일 코드 파일로 만드는 것입니다. 사용자 지정 `My` 확장을 만드는 방법에 대 한 자세한 내용과 지침은 [Visual Basic에서 My 네임 스페이스 확장](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)을 참조 하세요.

## <a name="export-a-my-namespace-extension-as-an-item-template"></a>My 네임 스페이스 확장을 항목 템플릿으로 내보내기

`My` 네임 스페이스 확장을 포함 하는 코드 파일을 만든 후에는 코드 파일을 Visual Studio 항목 템플릿으로 내보낼 수 있습니다. Visual Studio 항목 템플릿으로 파일을 내보내는 방법에 대 한 지침은 [방법: 항목 템플릿 만들기](/visualstudio/ide/how-to-create-item-templates)를 참조 하세요.

> [!NOTE]
> `My` 네임 스페이스 확장이 특정 어셈블리에 종속 되어 있는 경우 해당 어셈블리에 대 한 참조가 추가 되 면 `My` 네임 스페이스 확장을 자동으로 설치 하도록 항목 템플릿을 사용자 지정할 수 있습니다. 결과적으로 코드 파일을 Visual Studio 항목 템플릿으로 내보낼 때 해당 어셈블리 참조를 제외 하려고 할 것입니다.

## <a name="customize-the-item-template"></a>항목 템플릿 사용자 지정

Visual Basic 프로젝트 디자이너의 **내 확장** 페이지에서 항목 템플릿을 관리할 수 있도록 설정할 수 있습니다. 지정 된 어셈블리에 대 한 참조가 프로젝트에 추가 될 때 항목 템플릿이 자동으로 추가 되도록 설정할 수도 있습니다. 이러한 사용자 지정을 사용 하려면 CustomData 파일 이라는 새 파일을 템플릿에 추가 하 고 .vstemplate 파일의 XML에 새 요소를 추가 합니다.

### <a name="add-the-customdata-file"></a>CustomData 파일 추가

CustomData 파일은 파일 이름 확장명이 인 텍스트 파일입니다. CustomData (파일 이름은 템플릿에 의미 있는 값으로 설정할 수 있으며 XML이 포함 되어 있습니다. CustomData 파일의 XML은 사용자가 Visual Basic 프로젝트 디자이너의 **내 확장** 페이지를 사용할 때 `My` 확장을 포함 하도록 Visual Basic에 지시 합니다. 필요에 따라 <`AssemblyFullName>` 특성을 CustomData 파일 XML에 추가할 수 있습니다. 이렇게 하면 특정 어셈블리에 대 한 참조가 프로젝트에 추가 될 때 사용자 지정 `My` 확장을 자동으로 설치 Visual Basic. 모든 텍스트 편집기나 XML 편집기를 사용 하 여 CustomData 파일을 만든 다음 항목 템플릿의 압축 폴더 (.zip 파일)에 추가할 수 있습니다.

예를 들어, 다음 XML에서는 Microsoft.visualbasic 어셈블리에 대 한 참조가 프로젝트에 추가 될 때 Visual Basic 프로젝트의 My Extensions 폴더에 템플릿 항목을 추가 하는 CustomData 파일의 내용을 보여 줍니다.

```xml
<VBMyExtensionTemplate
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"
    Version="1.0.0.0"
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"
/>
```

CustomData 파일에는 다음 표에 나열 된 특성을 포함 하는 <`VBMyExtensionTemplate>` 요소가 포함 되어 있습니다.

|특성|설명|
|---|---|
|`ID`|필수입니다. 확장 프로그램에 대 한 고유 식별자입니다. 이 ID를 가진 확장이 프로젝트에 이미 추가 된 경우 사용자에 게 다시 추가 하 라는 메시지가 표시 되지 않습니다.|
|`Version`|필수입니다. 항목 템플릿에 대 한 버전 번호입니다.|
|`AssemblyFullName`|(선택 사항) 어셈블리 이름입니다. 이 어셈블리에 대 한 참조가 프로젝트에 추가 되 면 사용자에 게이 항목 템플릿에서 `My` 확장을 추가할지 묻는 메시지가 표시 됩니다.|

### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a>.Vstemplate 파일에 \<CustomDataSignature > 요소를 추가 합니다.

Visual Studio 항목 템플릿을 `My` 네임 스페이스 확장으로 식별 하려면 항목 템플릿에 대 한 .vstemplate 파일도 수정 해야 합니다. `<TemplateData>` 요소에 `<CustomDataSignature>` 요소를 추가 해야 합니다. `<CustomDataSignature>` 요소는 다음 예제와 같이 텍스트 `Microsoft.VisualBasic.MyExtension`를 포함 해야 합니다.

```xml
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>
```

압축 된 폴더 (.zip 파일)의 파일은 직접 수정할 수 없습니다. 압축 된 폴더에서 .vstemplate 파일을 복사 하 고 수정한 다음 압축 폴더의 .vstemplate 파일을 업데이트 된 복사본으로 바꾸어야 합니다.

다음 예제에서는 `<CustomDataSignature>` 요소가 추가 된 .vstemplate 파일의 내용을 보여 줍니다.

```xml
<VSTemplate Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">
  <TemplateData>
    <DefaultName>MyCustomExtensionModule.vb</DefaultName>
    <Name>MyPrinterInfo</Name>
    <Description>Custom My Extensions Item Template</Description>
    <ProjectType>VisualBasic</ProjectType>
    <SortOrder>10</SortOrder>
    <Icon>__TemplateIcon.ico</Icon>
    <CustomDataSignature      >Microsoft.VisualBasic.MyExtension</CustomDataSignature>
  </TemplateData>
  <TemplateContent>
    <References />
    <ProjectItem SubType="Code"
                 TargetFileName="$fileinputname$.vb"
                 ReplaceParameters="true"
     >MyCustomExtensionModule.vb</ProjectItem>
  </TemplateContent>
</VSTemplate>
```

## <a name="install-the-template"></a>템플릿 설치

템플릿을 설치 하려면 압축 폴더 ( *.zip* 파일)를 Visual Basic 항목 템플릿 폴더에 복사할 수 있습니다. 기본적으로 사용자 항목 템플릿은 *%USERPROFILE%\Documents\Visual Studio \<버전\>\Templates\ItemTemplates\Visual Basic*에 있습니다. 또는 템플릿을 Visual Studio 설치 관리자 ( *.vsi*) 파일로 게시할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [Visual Basic의 내 네임스페이스 확장](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)
- [Visual Basic 애플리케이션 모델 확장](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)
- [My에 사용할 수 있는 개체 사용자 지정](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
- [내 확장명 페이지, 프로젝트 디자이너](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
