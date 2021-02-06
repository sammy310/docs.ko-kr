---
description: '자세히 알아보기: 응용 프로그램 설정 스키마'
title: 응용 프로그램 설정 스키마
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
ms.openlocfilehash: 24c5771e9d98d07bbdc8dab5fce0f1535bc9b582
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652902"
---
# <a name="application-settings-schema"></a><span data-ttu-id="59103-103">응용 프로그램 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="59103-103">Application Settings schema</span></span>

<span data-ttu-id="59103-104">응용 프로그램 설정을 통해 Windows Forms 또는 ASP.NET 응용 프로그램에서 응용 프로그램 범위 및 사용자 범위 설정을 저장 하 고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59103-104">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="59103-105">이 컨텍스트에서 *설정은* 응용 프로그램 또는 현재 사용자와 관련 된 정보 이며, 데이터베이스 연결 문자열에서 사용자의 기본 설정 기본 창 크기에 이르기까지 모든 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="59103-105">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="59103-106">기본적으로 Windows Forms 응용 프로그램의 응용 프로그램 설정은 <xref:System.Configuration.LocalFileSettingsProvider> 클래스를 사용 합니다 .이 클래스는 .net 구성 시스템을 사용 하 여 설정을 XML 구성 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="59103-106">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="59103-107">응용 프로그램 설정에 사용 되는 파일에 대 한 자세한 내용은 [응용 프로그램 설정 아키텍처](/dotnet/desktop/winforms/advanced/application-settings-architecture)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="59103-107">For more information about the files used by application settings, see [Application Settings Architecture](/dotnet/desktop/winforms/advanced/application-settings-architecture).</span></span>

<span data-ttu-id="59103-108">응용 프로그램 설정은 사용 하는 구성 파일의 일부로 다음 요소를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="59103-108">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="59103-109">요소</span><span class="sxs-lookup"><span data-stu-id="59103-109">Element</span></span>                    | <span data-ttu-id="59103-110">설명</span><span class="sxs-lookup"><span data-stu-id="59103-110">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| **\<applicationSettings>** | <span data-ttu-id="59103-111">**\<setting>** 응용 프로그램과 관련 된 모든 태그를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="59103-111">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| **\<userSettings>**        | <span data-ttu-id="59103-112">**\<setting>** 현재 사용자와 관련 된 모든 태그를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="59103-112">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| **\<setting>**             | <span data-ttu-id="59103-113">설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="59103-113">Defines a setting.</span></span> <span data-ttu-id="59103-114">또는의 자식 **\<applicationSettings>** 입니다 **\<userSettings>** .</span><span class="sxs-lookup"><span data-stu-id="59103-114">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| **\<value>**               | <span data-ttu-id="59103-115">설정 값을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="59103-115">Defines a setting's value.</span></span> <span data-ttu-id="59103-116">의 자식 **\<setting>** 입니다.</span><span class="sxs-lookup"><span data-stu-id="59103-116">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="59103-117">\<applicationSettings> 요소</span><span class="sxs-lookup"><span data-stu-id="59103-117">\<applicationSettings> element</span></span>

<span data-ttu-id="59103-118">이 요소는 **\<setting>** 클라이언트 컴퓨터의 응용 프로그램 인스턴스와 관련 된 모든 태그를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="59103-118">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="59103-119">특성 없음을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="59103-119">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="59103-120">\<userSettings> 요소</span><span class="sxs-lookup"><span data-stu-id="59103-120">\<userSettings> element</span></span>

<span data-ttu-id="59103-121">이 요소는 현재 응용 프로그램을 사용 하 고 있는 사용자에 해당 하는 모든 태그를 포함 **\<setting>** 합니다.</span><span class="sxs-lookup"><span data-stu-id="59103-121">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="59103-122">특성 없음을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="59103-122">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="59103-123">\<setting> 요소</span><span class="sxs-lookup"><span data-stu-id="59103-123">\<setting> element</span></span>

<span data-ttu-id="59103-124">이 요소는 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="59103-124">This element defines a setting.</span></span> <span data-ttu-id="59103-125">여기에는 다음과 같은 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59103-125">It has the following attributes.</span></span>

| <span data-ttu-id="59103-126">attribute</span><span class="sxs-lookup"><span data-stu-id="59103-126">Attribute</span></span>        | <span data-ttu-id="59103-127">설명</span><span class="sxs-lookup"><span data-stu-id="59103-127">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="59103-128">**name**</span><span class="sxs-lookup"><span data-stu-id="59103-128">**name**</span></span>         | <span data-ttu-id="59103-129">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="59103-129">Required.</span></span> <span data-ttu-id="59103-130">설정의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="59103-130">The unique ID of the setting.</span></span> <span data-ttu-id="59103-131">Visual Studio를 통해 만든 설정은 이름으로 저장 됩니다 `ProjectName.Properties.Settings` .</span><span class="sxs-lookup"><span data-stu-id="59103-131">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="59103-132">**serializeAs**</span><span class="sxs-lookup"><span data-stu-id="59103-132">**serializeAs**</span></span> | <span data-ttu-id="59103-133">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="59103-133">Required.</span></span> <span data-ttu-id="59103-134">값을 텍스트로 직렬화 하는 데 사용할 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="59103-134">The format to use for serializing the value to text.</span></span> <span data-ttu-id="59103-135">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="59103-135">Valid values are:</span></span><br><br><span data-ttu-id="59103-136">- `string`.</span><span class="sxs-lookup"><span data-stu-id="59103-136">- `string`.</span></span> <span data-ttu-id="59103-137">값은을 사용 하 여 문자열로 serialize 됩니다 <xref:System.ComponentModel.TypeConverter> .</span><span class="sxs-lookup"><span data-stu-id="59103-137">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="59103-138">- `xml`.</span><span class="sxs-lookup"><span data-stu-id="59103-138">- `xml`.</span></span> <span data-ttu-id="59103-139">값은 XML 직렬화를 사용 하 여 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59103-139">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="59103-140">- `binary`.</span><span class="sxs-lookup"><span data-stu-id="59103-140">- `binary`.</span></span> <span data-ttu-id="59103-141">이 값은 이진 serialization을 사용 하 여 텍스트 인코딩 이진으로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59103-141">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="59103-142">- `custom`.</span><span class="sxs-lookup"><span data-stu-id="59103-142">- `custom`.</span></span> <span data-ttu-id="59103-143">설정 공급자는이 설정에 대 한 기본적인 지식을 갖고 있으며 직렬화 및 역직렬화 합니다.</span><span class="sxs-lookup"><span data-stu-id="59103-143">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="59103-144">\<value> 요소</span><span class="sxs-lookup"><span data-stu-id="59103-144">\<value> element</span></span>

<span data-ttu-id="59103-145">이 요소는 설정 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="59103-145">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="59103-146">예제</span><span class="sxs-lookup"><span data-stu-id="59103-146">Example</span></span>

<span data-ttu-id="59103-147">다음 예제에서는 두 개의 응용 프로그램 범위 설정 및 두 개의 사용자 범위 설정을 정의 하는 응용 프로그램 설정 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="59103-147">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
    </sectionGroup>
    <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" allowExeDefinition="MachineToLocalUser" />
    </sectionGroup>
  </configSections>
  <applicationSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="Cursor" serializeAs="String">
        <value>Default</value>
      </setting>
      <setting name="DoubleBuffering" serializeAs="String">
        <value>False</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </applicationSettings>
  <userSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="FormTitle" serializeAs="String">
        <value>Form1</value>
      </setting>
      <setting name="FormSize" serializeAs="String">
        <value>595, 536</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </userSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="59103-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59103-148">See also</span></span>

- [<span data-ttu-id="59103-149">애플리케이션 설정 개요</span><span class="sxs-lookup"><span data-stu-id="59103-149">Application Settings Overview</span></span>](/dotnet/desktop/winforms/advanced/application-settings-overview)
- [<span data-ttu-id="59103-150">애플리케이션 설정 아키텍처</span><span class="sxs-lookup"><span data-stu-id="59103-150">Application Settings Architecture</span></span>](/dotnet/desktop/winforms/advanced/application-settings-architecture)
