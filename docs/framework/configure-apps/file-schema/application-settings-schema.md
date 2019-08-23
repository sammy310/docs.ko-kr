---
title: 응용 프로그램 설정 스키마
ms.date: 03/30/2017
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
ms.openlocfilehash: 89a08434332b0242fe57e9dcaa3b3ebcc5692d06
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927756"
---
# <a name="application-settings-schema"></a><span data-ttu-id="8a4a9-102">응용 프로그램 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="8a4a9-102">Application Settings schema</span></span>

<span data-ttu-id="8a4a9-103">응용 프로그램 설정을 통해 Windows Forms 또는 ASP.NET 응용 프로그램에서 응용 프로그램 범위 및 사용자 범위 설정을 저장 하 고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-103">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="8a4a9-104">이 컨텍스트에서 *설정은* 응용 프로그램 또는 현재 사용자와 관련 된 정보 이며, 데이터베이스 연결 문자열에서 사용자의 기본 설정 기본 창 크기에 이르기까지 모든 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-104">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="8a4a9-105">기본적으로 Windows Forms 응용 프로그램의 응용 프로그램 설정은 <xref:System.Configuration.LocalFileSettingsProvider> 클래스를 사용 합니다 .이 클래스는 .net 구성 시스템을 사용 하 여 설정을 XML 구성 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-105">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="8a4a9-106">응용 프로그램 설정에 사용 되는 파일에 대 한 자세한 내용은 [응용 프로그램 설정 아키텍처](../../winforms/advanced/application-settings-architecture.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-106">For more information about the files used by application settings, see [Application Settings Architecture](../../winforms/advanced/application-settings-architecture.md).</span></span>

<span data-ttu-id="8a4a9-107">응용 프로그램 설정은 사용 하는 구성 파일의 일부로 다음 요소를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-107">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="8a4a9-108">요소</span><span class="sxs-lookup"><span data-stu-id="8a4a9-108">Element</span></span>                    | <span data-ttu-id="8a4a9-109">Description</span><span class="sxs-lookup"><span data-stu-id="8a4a9-109">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="8a4a9-110">**\<applicationSettings>**</span><span class="sxs-lookup"><span data-stu-id="8a4a9-110">**\<applicationSettings>**</span></span> | <span data-ttu-id="8a4a9-111">응용 프로그램에 특정 한 모든  **\<설정 >** 태그를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-111">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| <span data-ttu-id="8a4a9-112">**\<userSettings>**</span><span class="sxs-lookup"><span data-stu-id="8a4a9-112">**\<userSettings>**</span></span>        | <span data-ttu-id="8a4a9-113">현재 사용자와 관련 된 모든  **\<설정 >** 태그를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-113">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| <span data-ttu-id="8a4a9-114">**\<setting>**</span><span class="sxs-lookup"><span data-stu-id="8a4a9-114">**\<setting>**</span></span>             | <span data-ttu-id="8a4a9-115">설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-115">Defines a setting.</span></span> <span data-ttu-id="8a4a9-116">Applicationsettings > 또는  **\<userSettings >** 의  **\<** 자식입니다.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-116">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| <span data-ttu-id="8a4a9-117">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="8a4a9-117">**\<value>**</span></span>               | <span data-ttu-id="8a4a9-118">설정 값을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-118">Defines a setting's value.</span></span> <span data-ttu-id="8a4a9-119">**\<설정 >** 의 자식입니다.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-119">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="8a4a9-120">\<applicationSettings > 요소</span><span class="sxs-lookup"><span data-stu-id="8a4a9-120">\<applicationSettings> element</span></span>

<span data-ttu-id="8a4a9-121">이 요소는 클라이언트 컴퓨터의 응용 프로그램 인스턴스와 관련 된 모든  **\<설정 >** 태그를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-121">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="8a4a9-122">특성 없음을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-122">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="8a4a9-123">\<userSettings > 요소</span><span class="sxs-lookup"><span data-stu-id="8a4a9-123">\<userSettings> element</span></span>

<span data-ttu-id="8a4a9-124">이 요소는 현재 응용 프로그램을 사용 하 고 있는 사용자에 해당 하는 모든  **\<설정 >** 태그를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-124">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="8a4a9-125">특성 없음을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-125">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="8a4a9-126">\<> 요소 설정</span><span class="sxs-lookup"><span data-stu-id="8a4a9-126">\<setting> element</span></span>

<span data-ttu-id="8a4a9-127">이 요소는 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-127">This element defines a setting.</span></span> <span data-ttu-id="8a4a9-128">여기에는 다음과 같은 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-128">It has the following attributes.</span></span>

| <span data-ttu-id="8a4a9-129">특성</span><span class="sxs-lookup"><span data-stu-id="8a4a9-129">Attribute</span></span>        | <span data-ttu-id="8a4a9-130">설명</span><span class="sxs-lookup"><span data-stu-id="8a4a9-130">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="8a4a9-131">**name**</span><span class="sxs-lookup"><span data-stu-id="8a4a9-131">**name**</span></span>         | <span data-ttu-id="8a4a9-132">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-132">Required.</span></span> <span data-ttu-id="8a4a9-133">설정의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-133">The unique ID of the setting.</span></span> <span data-ttu-id="8a4a9-134">Visual Studio를 통해 만든 설정은 이름 `ProjectName.Properties.Settings`으로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-134">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="8a4a9-135">**serializedAs**</span><span class="sxs-lookup"><span data-stu-id="8a4a9-135">**serializedAs**</span></span> | <span data-ttu-id="8a4a9-136">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-136">Required.</span></span> <span data-ttu-id="8a4a9-137">값을 텍스트로 직렬화 하는 데 사용할 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-137">The format to use for serializing the value to text.</span></span> <span data-ttu-id="8a4a9-138">유효한 값은</span><span class="sxs-lookup"><span data-stu-id="8a4a9-138">Valid values are:</span></span><br><br><span data-ttu-id="8a4a9-139">- `string`.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-139">- `string`.</span></span> <span data-ttu-id="8a4a9-140">값은을 <xref:System.ComponentModel.TypeConverter>사용 하 여 문자열로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-140">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="8a4a9-141">- `xml`.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-141">- `xml`.</span></span> <span data-ttu-id="8a4a9-142">값은 XML 직렬화를 사용 하 여 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-142">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="8a4a9-143">- `binary`.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-143">- `binary`.</span></span> <span data-ttu-id="8a4a9-144">이 값은 이진 serialization을 사용 하 여 텍스트 인코딩 이진으로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-144">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="8a4a9-145">- `custom`.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-145">- `custom`.</span></span> <span data-ttu-id="8a4a9-146">설정 공급자는이 설정에 대 한 기본적인 지식을 갖고 있으며 직렬화 및 역직렬화 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-146">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="8a4a9-147">\<value > 요소</span><span class="sxs-lookup"><span data-stu-id="8a4a9-147">\<value> element</span></span>

<span data-ttu-id="8a4a9-148">이 요소는 설정 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-148">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="8a4a9-149">예제</span><span class="sxs-lookup"><span data-stu-id="8a4a9-149">Example</span></span>

<span data-ttu-id="8a4a9-150">다음 예제에서는 두 개의 응용 프로그램 범위 설정 및 두 개의 사용자 범위 설정을 정의 하는 응용 프로그램 설정 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8a4a9-150">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="8a4a9-151">참고자료</span><span class="sxs-lookup"><span data-stu-id="8a4a9-151">See also</span></span>

- [<span data-ttu-id="8a4a9-152">응용 프로그램 설정 개요</span><span class="sxs-lookup"><span data-stu-id="8a4a9-152">Application Settings Overview</span></span>](../../winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="8a4a9-153">응용 프로그램 설정 아키텍처</span><span class="sxs-lookup"><span data-stu-id="8a4a9-153">Application Settings Architecture</span></span>](../../winforms/advanced/application-settings-architecture.md)
