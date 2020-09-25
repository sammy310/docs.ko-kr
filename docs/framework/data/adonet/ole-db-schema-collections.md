---
title: OLE DB 스키마 컬렉션
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 90899a123b3dafcd47a50ef8f6eb003938b22a03
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186941"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="535fb-102">OLE DB 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="535fb-102">OLE DB Schema Collections</span></span>

<span data-ttu-id="535fb-103">이 단원에서는 Microsoft SQL Server, Oracle 및 Microsoft Jet용 OLE DB 공급자에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="535fb-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="535fb-104">Microsoft SQL Server OLE DB 공급자</span><span class="sxs-lookup"><span data-stu-id="535fb-104">Microsoft SQL Server OLE DB Provider</span></span>  

 <span data-ttu-id="535fb-105">Microsoft SQL Server OLE DB Driver에서는 공통 스키마 컬렉션을 비롯하여 다음과 같은 특정 스키마 컬렉션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="535fb-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="535fb-106">테이블</span><span class="sxs-lookup"><span data-stu-id="535fb-106">Tables</span></span>  
  
- <span data-ttu-id="535fb-107">열</span><span class="sxs-lookup"><span data-stu-id="535fb-107">Columns</span></span>  
  
- <span data-ttu-id="535fb-108">프로시저</span><span class="sxs-lookup"><span data-stu-id="535fb-108">Procedures</span></span>  
  
- <span data-ttu-id="535fb-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="535fb-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="535fb-110">카탈로그</span><span class="sxs-lookup"><span data-stu-id="535fb-110">Catalog</span></span>  
  
- <span data-ttu-id="535fb-111">인덱스</span><span class="sxs-lookup"><span data-stu-id="535fb-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="535fb-112">테이블</span><span class="sxs-lookup"><span data-stu-id="535fb-112">Tables</span></span>  
  
|<span data-ttu-id="535fb-113">ColumnName</span><span class="sxs-lookup"><span data-stu-id="535fb-113">ColumnName</span></span>|<span data-ttu-id="535fb-114">DataType</span><span class="sxs-lookup"><span data-stu-id="535fb-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="535fb-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-115">TABLE_CATALOG</span></span>|<span data-ttu-id="535fb-116">String</span><span class="sxs-lookup"><span data-stu-id="535fb-116">String</span></span>|  
|<span data-ttu-id="535fb-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="535fb-118">String</span><span class="sxs-lookup"><span data-stu-id="535fb-118">String</span></span>|  
|<span data-ttu-id="535fb-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-119">TABLE_NAME</span></span>|<span data-ttu-id="535fb-120">String</span><span class="sxs-lookup"><span data-stu-id="535fb-120">String</span></span>|  
|<span data-ttu-id="535fb-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="535fb-121">TABLE_TYPE</span></span>|<span data-ttu-id="535fb-122">String</span><span class="sxs-lookup"><span data-stu-id="535fb-122">String</span></span>|  
|<span data-ttu-id="535fb-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-123">TABLE_GUID</span></span>|<span data-ttu-id="535fb-124">GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-124">Guid</span></span>|  
|<span data-ttu-id="535fb-125">설명</span><span class="sxs-lookup"><span data-stu-id="535fb-125">DESCRIPTION</span></span>|<span data-ttu-id="535fb-126">String</span><span class="sxs-lookup"><span data-stu-id="535fb-126">String</span></span>|  
|<span data-ttu-id="535fb-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="535fb-127">TABLE_PROPID</span></span>|<span data-ttu-id="535fb-128">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-128">Int64</span></span>|  
|<span data-ttu-id="535fb-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="535fb-129">DATE_CREATED</span></span>|<span data-ttu-id="535fb-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="535fb-130">DateTime</span></span>|  
|<span data-ttu-id="535fb-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="535fb-131">DATE_MODIFIED</span></span>|<span data-ttu-id="535fb-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="535fb-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="535fb-133">열</span><span class="sxs-lookup"><span data-stu-id="535fb-133">Columns</span></span>  
  
|<span data-ttu-id="535fb-134">ColumnName</span><span class="sxs-lookup"><span data-stu-id="535fb-134">ColumnName</span></span>|<span data-ttu-id="535fb-135">DataType</span><span class="sxs-lookup"><span data-stu-id="535fb-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="535fb-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-136">TABLE_CATALOG</span></span>|<span data-ttu-id="535fb-137">String</span><span class="sxs-lookup"><span data-stu-id="535fb-137">String</span></span>|  
|<span data-ttu-id="535fb-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="535fb-139">String</span><span class="sxs-lookup"><span data-stu-id="535fb-139">String</span></span>|  
|<span data-ttu-id="535fb-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-140">TABLE_NAME</span></span>|<span data-ttu-id="535fb-141">String</span><span class="sxs-lookup"><span data-stu-id="535fb-141">String</span></span>|  
|<span data-ttu-id="535fb-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-142">COLUMN_NAME</span></span>|<span data-ttu-id="535fb-143">String</span><span class="sxs-lookup"><span data-stu-id="535fb-143">String</span></span>|  
|<span data-ttu-id="535fb-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-144">COLUMN_GUID</span></span>|<span data-ttu-id="535fb-145">GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-145">Guid</span></span>|  
|<span data-ttu-id="535fb-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="535fb-146">COLUMN_PROPID</span></span>|<span data-ttu-id="535fb-147">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-147">Int64</span></span>|  
|<span data-ttu-id="535fb-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="535fb-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="535fb-149">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-149">Int64</span></span>|  
|<span data-ttu-id="535fb-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="535fb-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="535fb-151">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-151">Boolean</span></span>|  
|<span data-ttu-id="535fb-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="535fb-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="535fb-153">String</span><span class="sxs-lookup"><span data-stu-id="535fb-153">String</span></span>|  
|<span data-ttu-id="535fb-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="535fb-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="535fb-155">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-155">Int64</span></span>|  
|<span data-ttu-id="535fb-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="535fb-156">IS_NULLABLE</span></span>|<span data-ttu-id="535fb-157">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-157">Boolean</span></span>|  
|<span data-ttu-id="535fb-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="535fb-158">DATA_TYPE</span></span>|<span data-ttu-id="535fb-159">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-159">Int32</span></span>|  
|<span data-ttu-id="535fb-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-160">TYPE_GUID</span></span>|<span data-ttu-id="535fb-161">GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-161">Guid</span></span>|  
|<span data-ttu-id="535fb-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="535fb-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="535fb-163">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-163">Int64</span></span>|  
|<span data-ttu-id="535fb-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="535fb-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="535fb-165">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-165">Int64</span></span>|  
|<span data-ttu-id="535fb-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="535fb-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="535fb-167">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-167">Int32</span></span>|  
|<span data-ttu-id="535fb-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="535fb-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="535fb-169">Int16</span><span class="sxs-lookup"><span data-stu-id="535fb-169">Int16</span></span>|  
|<span data-ttu-id="535fb-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="535fb-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="535fb-171">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-171">Int64</span></span>|  
|<span data-ttu-id="535fb-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="535fb-173">String</span><span class="sxs-lookup"><span data-stu-id="535fb-173">String</span></span>|  
|<span data-ttu-id="535fb-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="535fb-175">String</span><span class="sxs-lookup"><span data-stu-id="535fb-175">String</span></span>|  
|<span data-ttu-id="535fb-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="535fb-177">String</span><span class="sxs-lookup"><span data-stu-id="535fb-177">String</span></span>|  
|<span data-ttu-id="535fb-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="535fb-179">String</span><span class="sxs-lookup"><span data-stu-id="535fb-179">String</span></span>|  
|<span data-ttu-id="535fb-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="535fb-181">String</span><span class="sxs-lookup"><span data-stu-id="535fb-181">String</span></span>|  
|<span data-ttu-id="535fb-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-182">COLLATION_NAME</span></span>|<span data-ttu-id="535fb-183">String</span><span class="sxs-lookup"><span data-stu-id="535fb-183">String</span></span>|  
|<span data-ttu-id="535fb-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="535fb-185">String</span><span class="sxs-lookup"><span data-stu-id="535fb-185">String</span></span>|  
|<span data-ttu-id="535fb-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="535fb-187">String</span><span class="sxs-lookup"><span data-stu-id="535fb-187">String</span></span>|  
|<span data-ttu-id="535fb-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-188">DOMAIN_NAME</span></span>|<span data-ttu-id="535fb-189">String</span><span class="sxs-lookup"><span data-stu-id="535fb-189">String</span></span>|  
|<span data-ttu-id="535fb-190">설명</span><span class="sxs-lookup"><span data-stu-id="535fb-190">DESCRIPTION</span></span>|<span data-ttu-id="535fb-191">String</span><span class="sxs-lookup"><span data-stu-id="535fb-191">String</span></span>|  
|<span data-ttu-id="535fb-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="535fb-192">COLUMN_LCID</span></span>|<span data-ttu-id="535fb-193">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-193">Int32</span></span>|  
|<span data-ttu-id="535fb-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="535fb-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="535fb-195">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-195">Int32</span></span>|  
|<span data-ttu-id="535fb-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="535fb-196">COLUMN_SORTID</span></span>|<span data-ttu-id="535fb-197">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-197">Int32</span></span>|  
|<span data-ttu-id="535fb-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="535fb-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="535fb-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="535fb-199">Byte[]</span></span>|  
|<span data-ttu-id="535fb-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="535fb-200">IS_COMPUTED</span></span>|<span data-ttu-id="535fb-201">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="535fb-202">프로시저</span><span class="sxs-lookup"><span data-stu-id="535fb-202">Procedures</span></span>  
  
|<span data-ttu-id="535fb-203">ColumnName</span><span class="sxs-lookup"><span data-stu-id="535fb-203">ColumnName</span></span>|<span data-ttu-id="535fb-204">DataType</span><span class="sxs-lookup"><span data-stu-id="535fb-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="535fb-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="535fb-206">String</span><span class="sxs-lookup"><span data-stu-id="535fb-206">String</span></span>|  
|<span data-ttu-id="535fb-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="535fb-208">String</span><span class="sxs-lookup"><span data-stu-id="535fb-208">String</span></span>|  
|<span data-ttu-id="535fb-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="535fb-210">String</span><span class="sxs-lookup"><span data-stu-id="535fb-210">String</span></span>|  
|<span data-ttu-id="535fb-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="535fb-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="535fb-212">Int16</span><span class="sxs-lookup"><span data-stu-id="535fb-212">Int16</span></span>|  
|<span data-ttu-id="535fb-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="535fb-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="535fb-214">String</span><span class="sxs-lookup"><span data-stu-id="535fb-214">String</span></span>|  
|<span data-ttu-id="535fb-215">설명</span><span class="sxs-lookup"><span data-stu-id="535fb-215">DESCRIPTION</span></span>|<span data-ttu-id="535fb-216">String</span><span class="sxs-lookup"><span data-stu-id="535fb-216">String</span></span>|  
|<span data-ttu-id="535fb-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="535fb-217">DATE_CREATED</span></span>|<span data-ttu-id="535fb-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="535fb-218">DateTime</span></span>|  
|<span data-ttu-id="535fb-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="535fb-219">DATE_MODIFIED</span></span>|<span data-ttu-id="535fb-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="535fb-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="535fb-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="535fb-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="535fb-222">ColumnName</span><span class="sxs-lookup"><span data-stu-id="535fb-222">ColumnName</span></span>|<span data-ttu-id="535fb-223">DataType</span><span class="sxs-lookup"><span data-stu-id="535fb-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="535fb-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="535fb-225">String</span><span class="sxs-lookup"><span data-stu-id="535fb-225">String</span></span>|  
|<span data-ttu-id="535fb-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="535fb-227">String</span><span class="sxs-lookup"><span data-stu-id="535fb-227">String</span></span>|  
|<span data-ttu-id="535fb-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="535fb-229">String</span><span class="sxs-lookup"><span data-stu-id="535fb-229">String</span></span>|  
|<span data-ttu-id="535fb-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-230">PARAMETER_NAME</span></span>|<span data-ttu-id="535fb-231">String</span><span class="sxs-lookup"><span data-stu-id="535fb-231">String</span></span>|  
|<span data-ttu-id="535fb-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="535fb-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="535fb-233">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-233">Int32</span></span>|  
|<span data-ttu-id="535fb-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="535fb-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="535fb-235">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-235">Int32</span></span>|  
|<span data-ttu-id="535fb-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="535fb-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="535fb-237">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-237">Boolean</span></span>|  
|<span data-ttu-id="535fb-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="535fb-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="535fb-239">String</span><span class="sxs-lookup"><span data-stu-id="535fb-239">String</span></span>|  
|<span data-ttu-id="535fb-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="535fb-240">IS_NULLABLE</span></span>|<span data-ttu-id="535fb-241">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-241">Boolean</span></span>|  
|<span data-ttu-id="535fb-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="535fb-242">DATA_TYPE</span></span>|<span data-ttu-id="535fb-243">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-243">Int32</span></span>|  
|<span data-ttu-id="535fb-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="535fb-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="535fb-245">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-245">Int64</span></span>|  
|<span data-ttu-id="535fb-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="535fb-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="535fb-247">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-247">Int64</span></span>|  
|<span data-ttu-id="535fb-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="535fb-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="535fb-249">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-249">Int32</span></span>|  
|<span data-ttu-id="535fb-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="535fb-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="535fb-251">Int16</span><span class="sxs-lookup"><span data-stu-id="535fb-251">Int16</span></span>|  
|<span data-ttu-id="535fb-252">설명</span><span class="sxs-lookup"><span data-stu-id="535fb-252">DESCRIPTION</span></span>|<span data-ttu-id="535fb-253">String</span><span class="sxs-lookup"><span data-stu-id="535fb-253">String</span></span>|  
|<span data-ttu-id="535fb-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-254">TYPE_NAME</span></span>|<span data-ttu-id="535fb-255">String</span><span class="sxs-lookup"><span data-stu-id="535fb-255">String</span></span>|  
|<span data-ttu-id="535fb-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="535fb-257">String</span><span class="sxs-lookup"><span data-stu-id="535fb-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="535fb-258">카탈로그</span><span class="sxs-lookup"><span data-stu-id="535fb-258">Catalog</span></span>  
  
|<span data-ttu-id="535fb-259">ColumnName</span><span class="sxs-lookup"><span data-stu-id="535fb-259">ColumnName</span></span>|<span data-ttu-id="535fb-260">DataType</span><span class="sxs-lookup"><span data-stu-id="535fb-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="535fb-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-261">CATALOG_NAME</span></span>|<span data-ttu-id="535fb-262">String</span><span class="sxs-lookup"><span data-stu-id="535fb-262">String</span></span>|  
|<span data-ttu-id="535fb-263">설명</span><span class="sxs-lookup"><span data-stu-id="535fb-263">DESCRIPTION</span></span>|<span data-ttu-id="535fb-264">String</span><span class="sxs-lookup"><span data-stu-id="535fb-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="535fb-265">인덱스</span><span class="sxs-lookup"><span data-stu-id="535fb-265">Indexes</span></span>  
  
|<span data-ttu-id="535fb-266">ColumnName</span><span class="sxs-lookup"><span data-stu-id="535fb-266">ColumnName</span></span>|<span data-ttu-id="535fb-267">DataType</span><span class="sxs-lookup"><span data-stu-id="535fb-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="535fb-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-268">TABLE_CATALOG</span></span>|<span data-ttu-id="535fb-269">String</span><span class="sxs-lookup"><span data-stu-id="535fb-269">String</span></span>|  
|<span data-ttu-id="535fb-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="535fb-271">String</span><span class="sxs-lookup"><span data-stu-id="535fb-271">String</span></span>|  
|<span data-ttu-id="535fb-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-272">TABLE_NAME</span></span>|<span data-ttu-id="535fb-273">String</span><span class="sxs-lookup"><span data-stu-id="535fb-273">String</span></span>|  
|<span data-ttu-id="535fb-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-274">INDEX_CATALOG</span></span>|<span data-ttu-id="535fb-275">String</span><span class="sxs-lookup"><span data-stu-id="535fb-275">String</span></span>|  
|<span data-ttu-id="535fb-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="535fb-277">String</span><span class="sxs-lookup"><span data-stu-id="535fb-277">String</span></span>|  
|<span data-ttu-id="535fb-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-278">INDEX_NAME</span></span>|<span data-ttu-id="535fb-279">String</span><span class="sxs-lookup"><span data-stu-id="535fb-279">String</span></span>|  
|<span data-ttu-id="535fb-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="535fb-280">PRIMARY_KEY</span></span>|<span data-ttu-id="535fb-281">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-281">Boolean</span></span>|  
|<span data-ttu-id="535fb-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="535fb-282">UNIQUE</span></span>|<span data-ttu-id="535fb-283">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-283">Boolean</span></span>|  
|<span data-ttu-id="535fb-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="535fb-284">CLUSTERED</span></span>|<span data-ttu-id="535fb-285">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-285">Boolean</span></span>|  
|<span data-ttu-id="535fb-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="535fb-286">TYPE</span></span>|<span data-ttu-id="535fb-287">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-287">Int32</span></span>|  
|<span data-ttu-id="535fb-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="535fb-288">FILL_FACTOR</span></span>|<span data-ttu-id="535fb-289">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-289">Int32</span></span>|  
|<span data-ttu-id="535fb-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="535fb-290">INITIAL_SIZE</span></span>|<span data-ttu-id="535fb-291">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-291">Int32</span></span>|  
|<span data-ttu-id="535fb-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="535fb-292">NULLS</span></span>|<span data-ttu-id="535fb-293">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-293">Int32</span></span>|  
|<span data-ttu-id="535fb-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="535fb-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="535fb-295">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-295">Boolean</span></span>|  
|<span data-ttu-id="535fb-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="535fb-296">AUTO_UPDATE</span></span>|<span data-ttu-id="535fb-297">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-297">Boolean</span></span>|  
|<span data-ttu-id="535fb-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="535fb-298">NULL_COLLATION</span></span>|<span data-ttu-id="535fb-299">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-299">Int32</span></span>|  
|<span data-ttu-id="535fb-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="535fb-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="535fb-301">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-301">Int64</span></span>|  
|<span data-ttu-id="535fb-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-302">COLUMN_NAME</span></span>|<span data-ttu-id="535fb-303">String</span><span class="sxs-lookup"><span data-stu-id="535fb-303">String</span></span>|  
|<span data-ttu-id="535fb-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-304">COLUMN_GUID</span></span>|<span data-ttu-id="535fb-305">GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-305">Guid</span></span>|  
|<span data-ttu-id="535fb-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="535fb-306">COLUMN_PROPID</span></span>|<span data-ttu-id="535fb-307">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-307">Int64</span></span>|  
|<span data-ttu-id="535fb-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="535fb-308">COLLATION</span></span>|<span data-ttu-id="535fb-309">Int16</span><span class="sxs-lookup"><span data-stu-id="535fb-309">Int16</span></span>|  
|<span data-ttu-id="535fb-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="535fb-310">CARDINALITY</span></span>|<span data-ttu-id="535fb-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="535fb-311">Decimal</span></span>|  
|<span data-ttu-id="535fb-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="535fb-312">PAGES</span></span>|<span data-ttu-id="535fb-313">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-313">Int32</span></span>|  
|<span data-ttu-id="535fb-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="535fb-314">FILTER_CONDITION</span></span>|<span data-ttu-id="535fb-315">String</span><span class="sxs-lookup"><span data-stu-id="535fb-315">String</span></span>|  
|<span data-ttu-id="535fb-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="535fb-316">INTEGRATED</span></span>|<span data-ttu-id="535fb-317">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="535fb-318">Microsoft Oracle OLE DB</span><span class="sxs-lookup"><span data-stu-id="535fb-318">Microsoft Oracle OLE DB Provider</span></span>  

 <span data-ttu-id="535fb-319">Microsoft Oracle OLE DB Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="535fb-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="535fb-320">테이블</span><span class="sxs-lookup"><span data-stu-id="535fb-320">Tables</span></span>  
  
- <span data-ttu-id="535fb-321">열</span><span class="sxs-lookup"><span data-stu-id="535fb-321">Columns</span></span>  
  
- <span data-ttu-id="535fb-322">프로시저</span><span class="sxs-lookup"><span data-stu-id="535fb-322">Procedures</span></span>  
  
- <span data-ttu-id="535fb-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="535fb-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="535fb-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="535fb-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="535fb-325">보기</span><span class="sxs-lookup"><span data-stu-id="535fb-325">Views</span></span>  
  
- <span data-ttu-id="535fb-326">인덱스</span><span class="sxs-lookup"><span data-stu-id="535fb-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="535fb-327">테이블</span><span class="sxs-lookup"><span data-stu-id="535fb-327">Tables</span></span>  
  
|<span data-ttu-id="535fb-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="535fb-328">ColumnName</span></span>|<span data-ttu-id="535fb-329">DataType</span><span class="sxs-lookup"><span data-stu-id="535fb-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="535fb-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-330">TABLE_CATALOG</span></span>|<span data-ttu-id="535fb-331">String</span><span class="sxs-lookup"><span data-stu-id="535fb-331">String</span></span>|  
|<span data-ttu-id="535fb-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="535fb-333">String</span><span class="sxs-lookup"><span data-stu-id="535fb-333">String</span></span>|  
|<span data-ttu-id="535fb-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-334">TABLE_NAME</span></span>|<span data-ttu-id="535fb-335">String</span><span class="sxs-lookup"><span data-stu-id="535fb-335">String</span></span>|  
|<span data-ttu-id="535fb-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="535fb-336">TABLE_TYPE</span></span>|<span data-ttu-id="535fb-337">String</span><span class="sxs-lookup"><span data-stu-id="535fb-337">String</span></span>|  
|<span data-ttu-id="535fb-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-338">TABLE_GUID</span></span>|<span data-ttu-id="535fb-339">GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-339">Guid</span></span>|  
|<span data-ttu-id="535fb-340">설명</span><span class="sxs-lookup"><span data-stu-id="535fb-340">DESCRIPTION</span></span>|<span data-ttu-id="535fb-341">String</span><span class="sxs-lookup"><span data-stu-id="535fb-341">String</span></span>|  
|<span data-ttu-id="535fb-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="535fb-342">TABLE_PROPID</span></span>|<span data-ttu-id="535fb-343">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-343">Int64</span></span>|  
|<span data-ttu-id="535fb-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="535fb-344">DATE_CREATED</span></span>|<span data-ttu-id="535fb-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="535fb-345">DateTime</span></span>|  
|<span data-ttu-id="535fb-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="535fb-346">DATE_MODIFIED</span></span>|<span data-ttu-id="535fb-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="535fb-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="535fb-348">열</span><span class="sxs-lookup"><span data-stu-id="535fb-348">Columns</span></span>  
  
|<span data-ttu-id="535fb-349">ColumnName</span><span class="sxs-lookup"><span data-stu-id="535fb-349">ColumnName</span></span>|<span data-ttu-id="535fb-350">DataType</span><span class="sxs-lookup"><span data-stu-id="535fb-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="535fb-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-351">TABLE_CATALOG</span></span>|<span data-ttu-id="535fb-352">String</span><span class="sxs-lookup"><span data-stu-id="535fb-352">String</span></span>|  
|<span data-ttu-id="535fb-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="535fb-354">String</span><span class="sxs-lookup"><span data-stu-id="535fb-354">String</span></span>|  
|<span data-ttu-id="535fb-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-355">TABLE_NAME</span></span>|<span data-ttu-id="535fb-356">String</span><span class="sxs-lookup"><span data-stu-id="535fb-356">String</span></span>|  
|<span data-ttu-id="535fb-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-357">COLUMN_NAME</span></span>|<span data-ttu-id="535fb-358">String</span><span class="sxs-lookup"><span data-stu-id="535fb-358">String</span></span>|  
|<span data-ttu-id="535fb-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-359">COLUMN_GUID</span></span>|<span data-ttu-id="535fb-360">GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-360">Guid</span></span>|  
|<span data-ttu-id="535fb-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="535fb-361">COLUMN_PROPID</span></span>|<span data-ttu-id="535fb-362">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-362">Int64</span></span>|  
|<span data-ttu-id="535fb-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="535fb-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="535fb-364">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-364">Int64</span></span>|  
|<span data-ttu-id="535fb-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="535fb-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="535fb-366">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-366">Boolean</span></span>|  
|<span data-ttu-id="535fb-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="535fb-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="535fb-368">String</span><span class="sxs-lookup"><span data-stu-id="535fb-368">String</span></span>|  
|<span data-ttu-id="535fb-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="535fb-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="535fb-370">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-370">Int64</span></span>|  
|<span data-ttu-id="535fb-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="535fb-371">IS_NULLABLE</span></span>|<span data-ttu-id="535fb-372">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-372">Boolean</span></span>|  
|<span data-ttu-id="535fb-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="535fb-373">DATA_TYPE</span></span>|<span data-ttu-id="535fb-374">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-374">Int32</span></span>|  
|<span data-ttu-id="535fb-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-375">TYPE_GUID</span></span>|<span data-ttu-id="535fb-376">GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-376">Guid</span></span>|  
|<span data-ttu-id="535fb-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="535fb-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="535fb-378">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-378">Int64</span></span>|  
|<span data-ttu-id="535fb-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="535fb-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="535fb-380">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-380">Int64</span></span>|  
|<span data-ttu-id="535fb-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="535fb-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="535fb-382">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-382">Int32</span></span>|  
|<span data-ttu-id="535fb-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="535fb-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="535fb-384">Int16</span><span class="sxs-lookup"><span data-stu-id="535fb-384">Int16</span></span>|  
|<span data-ttu-id="535fb-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="535fb-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="535fb-386">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-386">Int64</span></span>|  
|<span data-ttu-id="535fb-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="535fb-388">String</span><span class="sxs-lookup"><span data-stu-id="535fb-388">String</span></span>|  
|<span data-ttu-id="535fb-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="535fb-390">String</span><span class="sxs-lookup"><span data-stu-id="535fb-390">String</span></span>|  
|<span data-ttu-id="535fb-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="535fb-392">String</span><span class="sxs-lookup"><span data-stu-id="535fb-392">String</span></span>|  
|<span data-ttu-id="535fb-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="535fb-394">String</span><span class="sxs-lookup"><span data-stu-id="535fb-394">String</span></span>|  
|<span data-ttu-id="535fb-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="535fb-396">String</span><span class="sxs-lookup"><span data-stu-id="535fb-396">String</span></span>|  
|<span data-ttu-id="535fb-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-397">COLLATION_NAME</span></span>|<span data-ttu-id="535fb-398">String</span><span class="sxs-lookup"><span data-stu-id="535fb-398">String</span></span>|  
|<span data-ttu-id="535fb-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="535fb-400">String</span><span class="sxs-lookup"><span data-stu-id="535fb-400">String</span></span>|  
|<span data-ttu-id="535fb-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="535fb-402">String</span><span class="sxs-lookup"><span data-stu-id="535fb-402">String</span></span>|  
|<span data-ttu-id="535fb-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-403">DOMAIN_NAME</span></span>|<span data-ttu-id="535fb-404">String</span><span class="sxs-lookup"><span data-stu-id="535fb-404">String</span></span>|  
|<span data-ttu-id="535fb-405">설명</span><span class="sxs-lookup"><span data-stu-id="535fb-405">DESCRIPTION</span></span>|<span data-ttu-id="535fb-406">String</span><span class="sxs-lookup"><span data-stu-id="535fb-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="535fb-407">프로시저</span><span class="sxs-lookup"><span data-stu-id="535fb-407">Procedures</span></span>  
  
|<span data-ttu-id="535fb-408">ColumnName</span><span class="sxs-lookup"><span data-stu-id="535fb-408">ColumnName</span></span>|<span data-ttu-id="535fb-409">DataType</span><span class="sxs-lookup"><span data-stu-id="535fb-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="535fb-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="535fb-411">String</span><span class="sxs-lookup"><span data-stu-id="535fb-411">String</span></span>|  
|<span data-ttu-id="535fb-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="535fb-413">String</span><span class="sxs-lookup"><span data-stu-id="535fb-413">String</span></span>|  
|<span data-ttu-id="535fb-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="535fb-415">String</span><span class="sxs-lookup"><span data-stu-id="535fb-415">String</span></span>|  
|<span data-ttu-id="535fb-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="535fb-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="535fb-417">Int16</span><span class="sxs-lookup"><span data-stu-id="535fb-417">Int16</span></span>|  
|<span data-ttu-id="535fb-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="535fb-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="535fb-419">String</span><span class="sxs-lookup"><span data-stu-id="535fb-419">String</span></span>|  
|<span data-ttu-id="535fb-420">설명</span><span class="sxs-lookup"><span data-stu-id="535fb-420">DESCRIPTION</span></span>|<span data-ttu-id="535fb-421">String</span><span class="sxs-lookup"><span data-stu-id="535fb-421">String</span></span>|  
|<span data-ttu-id="535fb-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="535fb-422">DATE_CREATED</span></span>|<span data-ttu-id="535fb-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="535fb-423">DateTime</span></span>|  
|<span data-ttu-id="535fb-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="535fb-424">DATE_MODIFIED</span></span>|<span data-ttu-id="535fb-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="535fb-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="535fb-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="535fb-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="535fb-427">ColumnName</span><span class="sxs-lookup"><span data-stu-id="535fb-427">ColumnName</span></span>|<span data-ttu-id="535fb-428">DataType</span><span class="sxs-lookup"><span data-stu-id="535fb-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="535fb-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="535fb-430">String</span><span class="sxs-lookup"><span data-stu-id="535fb-430">String</span></span>|  
|<span data-ttu-id="535fb-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="535fb-432">String</span><span class="sxs-lookup"><span data-stu-id="535fb-432">String</span></span>|  
|<span data-ttu-id="535fb-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="535fb-434">String</span><span class="sxs-lookup"><span data-stu-id="535fb-434">String</span></span>|  
|<span data-ttu-id="535fb-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-435">COLUMN_NAME</span></span>|<span data-ttu-id="535fb-436">String</span><span class="sxs-lookup"><span data-stu-id="535fb-436">String</span></span>|  
|<span data-ttu-id="535fb-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-437">COLUMN_GUID</span></span>|<span data-ttu-id="535fb-438">GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-438">Guid</span></span>|  
|<span data-ttu-id="535fb-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="535fb-439">COLUMN_PROPID</span></span>|<span data-ttu-id="535fb-440">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-440">Int64</span></span>|  
|<span data-ttu-id="535fb-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="535fb-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="535fb-442">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-442">Int64</span></span>|  
|<span data-ttu-id="535fb-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="535fb-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="535fb-444">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-444">Int64</span></span>|  
|<span data-ttu-id="535fb-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="535fb-445">IS_NULLABLE</span></span>|<span data-ttu-id="535fb-446">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-446">Boolean</span></span>|  
|<span data-ttu-id="535fb-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="535fb-447">DATA_TYPE</span></span>|<span data-ttu-id="535fb-448">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-448">Int32</span></span>|  
|<span data-ttu-id="535fb-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-449">TYPE_GUID</span></span>|<span data-ttu-id="535fb-450">GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-450">Guid</span></span>|  
|<span data-ttu-id="535fb-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="535fb-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="535fb-452">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-452">Int64</span></span>|  
|<span data-ttu-id="535fb-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="535fb-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="535fb-454">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-454">Int64</span></span>|  
|<span data-ttu-id="535fb-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="535fb-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="535fb-456">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-456">Int32</span></span>|  
|<span data-ttu-id="535fb-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="535fb-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="535fb-458">Int16</span><span class="sxs-lookup"><span data-stu-id="535fb-458">Int16</span></span>|  
|<span data-ttu-id="535fb-459">설명</span><span class="sxs-lookup"><span data-stu-id="535fb-459">DESCRIPTION</span></span>|<span data-ttu-id="535fb-460">String</span><span class="sxs-lookup"><span data-stu-id="535fb-460">String</span></span>|  
|<span data-ttu-id="535fb-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="535fb-461">OVERLOAD</span></span>|<span data-ttu-id="535fb-462">Int16</span><span class="sxs-lookup"><span data-stu-id="535fb-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="535fb-463">보기</span><span class="sxs-lookup"><span data-stu-id="535fb-463">Views</span></span>  
  
|<span data-ttu-id="535fb-464">ColumnName</span><span class="sxs-lookup"><span data-stu-id="535fb-464">ColumnName</span></span>|<span data-ttu-id="535fb-465">DataType</span><span class="sxs-lookup"><span data-stu-id="535fb-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="535fb-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-466">TABLE_CATALOG</span></span>|<span data-ttu-id="535fb-467">String</span><span class="sxs-lookup"><span data-stu-id="535fb-467">String</span></span>|  
|<span data-ttu-id="535fb-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="535fb-469">String</span><span class="sxs-lookup"><span data-stu-id="535fb-469">String</span></span>|  
|<span data-ttu-id="535fb-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-470">TABLE_NAME</span></span>|<span data-ttu-id="535fb-471">String</span><span class="sxs-lookup"><span data-stu-id="535fb-471">String</span></span>|  
|<span data-ttu-id="535fb-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="535fb-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="535fb-473">String</span><span class="sxs-lookup"><span data-stu-id="535fb-473">String</span></span>|  
|<span data-ttu-id="535fb-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="535fb-474">CHECK_OPTION</span></span>|<span data-ttu-id="535fb-475">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-475">Boolean</span></span>|  
|<span data-ttu-id="535fb-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="535fb-476">IS_UPDATABLE</span></span>|<span data-ttu-id="535fb-477">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-477">Boolean</span></span>|  
|<span data-ttu-id="535fb-478">설명</span><span class="sxs-lookup"><span data-stu-id="535fb-478">DESCRIPTION</span></span>|<span data-ttu-id="535fb-479">String</span><span class="sxs-lookup"><span data-stu-id="535fb-479">String</span></span>|  
|<span data-ttu-id="535fb-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="535fb-480">DATE_CREATED</span></span>|<span data-ttu-id="535fb-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="535fb-481">DateTime</span></span>|  
|<span data-ttu-id="535fb-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="535fb-482">DATE_MODIFIED</span></span>|<span data-ttu-id="535fb-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="535fb-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="535fb-484">인덱스</span><span class="sxs-lookup"><span data-stu-id="535fb-484">Indexes</span></span>  
  
|<span data-ttu-id="535fb-485">ColumnName</span><span class="sxs-lookup"><span data-stu-id="535fb-485">ColumnName</span></span>|<span data-ttu-id="535fb-486">DataType</span><span class="sxs-lookup"><span data-stu-id="535fb-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="535fb-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-487">TABLE_CATALOG</span></span>|<span data-ttu-id="535fb-488">String</span><span class="sxs-lookup"><span data-stu-id="535fb-488">String</span></span>|  
|<span data-ttu-id="535fb-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="535fb-490">String</span><span class="sxs-lookup"><span data-stu-id="535fb-490">String</span></span>|  
|<span data-ttu-id="535fb-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-491">TABLE_NAME</span></span>|<span data-ttu-id="535fb-492">String</span><span class="sxs-lookup"><span data-stu-id="535fb-492">String</span></span>|  
|<span data-ttu-id="535fb-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-493">INDEX_CATALOG</span></span>|<span data-ttu-id="535fb-494">String</span><span class="sxs-lookup"><span data-stu-id="535fb-494">String</span></span>|  
|<span data-ttu-id="535fb-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="535fb-496">String</span><span class="sxs-lookup"><span data-stu-id="535fb-496">String</span></span>|  
|<span data-ttu-id="535fb-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-497">INDEX_NAME</span></span>|<span data-ttu-id="535fb-498">String</span><span class="sxs-lookup"><span data-stu-id="535fb-498">String</span></span>|  
|<span data-ttu-id="535fb-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="535fb-499">PRIMARY_KEY</span></span>|<span data-ttu-id="535fb-500">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-500">Boolean</span></span>|  
|<span data-ttu-id="535fb-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="535fb-501">UNIQUE</span></span>|<span data-ttu-id="535fb-502">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-502">Boolean</span></span>|  
|<span data-ttu-id="535fb-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="535fb-503">CLUSTERED</span></span>|<span data-ttu-id="535fb-504">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-504">Boolean</span></span>|  
|<span data-ttu-id="535fb-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="535fb-505">TYPE</span></span>|<span data-ttu-id="535fb-506">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-506">Int32</span></span>|  
|<span data-ttu-id="535fb-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="535fb-507">FILL_FACTOR</span></span>|<span data-ttu-id="535fb-508">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-508">Int32</span></span>|  
|<span data-ttu-id="535fb-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="535fb-509">INITIAL_SIZE</span></span>|<span data-ttu-id="535fb-510">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-510">Int32</span></span>|  
|<span data-ttu-id="535fb-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="535fb-511">NULLS</span></span>|<span data-ttu-id="535fb-512">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-512">Int32</span></span>|  
|<span data-ttu-id="535fb-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="535fb-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="535fb-514">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-514">Boolean</span></span>|  
|<span data-ttu-id="535fb-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="535fb-515">AUTO_UPDATE</span></span>|<span data-ttu-id="535fb-516">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-516">Boolean</span></span>|  
|<span data-ttu-id="535fb-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="535fb-517">NULL_COLLATION</span></span>|<span data-ttu-id="535fb-518">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-518">Int32</span></span>|  
|<span data-ttu-id="535fb-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="535fb-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="535fb-520">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-520">Int64</span></span>|  
|<span data-ttu-id="535fb-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-521">COLUMN_NAME</span></span>|<span data-ttu-id="535fb-522">String</span><span class="sxs-lookup"><span data-stu-id="535fb-522">String</span></span>|  
|<span data-ttu-id="535fb-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-523">COLUMN_GUID</span></span>|<span data-ttu-id="535fb-524">GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-524">Guid</span></span>|  
|<span data-ttu-id="535fb-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="535fb-525">COLUMN_PROPID</span></span>|<span data-ttu-id="535fb-526">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-526">Int64</span></span>|  
|<span data-ttu-id="535fb-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="535fb-527">COLLATION</span></span>|<span data-ttu-id="535fb-528">Int16</span><span class="sxs-lookup"><span data-stu-id="535fb-528">Int16</span></span>|  
|<span data-ttu-id="535fb-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="535fb-529">CARDINALITY</span></span>|<span data-ttu-id="535fb-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="535fb-530">Decimal</span></span>|  
|<span data-ttu-id="535fb-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="535fb-531">PAGES</span></span>|<span data-ttu-id="535fb-532">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-532">Int32</span></span>|  
|<span data-ttu-id="535fb-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="535fb-533">FILTER_CONDITION</span></span>|<span data-ttu-id="535fb-534">String</span><span class="sxs-lookup"><span data-stu-id="535fb-534">String</span></span>|  
|<span data-ttu-id="535fb-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="535fb-535">INTEGRATED</span></span>|<span data-ttu-id="535fb-536">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="535fb-537">Microsoft Jet OLE DB</span><span class="sxs-lookup"><span data-stu-id="535fb-537">Microsoft Jet OLE DB Provider</span></span>  

 <span data-ttu-id="535fb-538">Microsoft Jet OLE DB Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="535fb-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="535fb-539">테이블</span><span class="sxs-lookup"><span data-stu-id="535fb-539">Tables</span></span>  
  
- <span data-ttu-id="535fb-540">열</span><span class="sxs-lookup"><span data-stu-id="535fb-540">Columns</span></span>  
  
- <span data-ttu-id="535fb-541">프로시저</span><span class="sxs-lookup"><span data-stu-id="535fb-541">Procedures</span></span>  
  
- <span data-ttu-id="535fb-542">보기</span><span class="sxs-lookup"><span data-stu-id="535fb-542">Views</span></span>  
  
- <span data-ttu-id="535fb-543">인덱스</span><span class="sxs-lookup"><span data-stu-id="535fb-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="535fb-544">테이블</span><span class="sxs-lookup"><span data-stu-id="535fb-544">Tables</span></span>  
  
|<span data-ttu-id="535fb-545">ColumnName</span><span class="sxs-lookup"><span data-stu-id="535fb-545">ColumnName</span></span>|<span data-ttu-id="535fb-546">DataType</span><span class="sxs-lookup"><span data-stu-id="535fb-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="535fb-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-547">TABLE_CATALOG</span></span>|<span data-ttu-id="535fb-548">String</span><span class="sxs-lookup"><span data-stu-id="535fb-548">String</span></span>|  
|<span data-ttu-id="535fb-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="535fb-550">String</span><span class="sxs-lookup"><span data-stu-id="535fb-550">String</span></span>|  
|<span data-ttu-id="535fb-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-551">TABLE_NAME</span></span>|<span data-ttu-id="535fb-552">String</span><span class="sxs-lookup"><span data-stu-id="535fb-552">String</span></span>|  
|<span data-ttu-id="535fb-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="535fb-553">TABLE_TYPE</span></span>|<span data-ttu-id="535fb-554">String</span><span class="sxs-lookup"><span data-stu-id="535fb-554">String</span></span>|  
|<span data-ttu-id="535fb-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-555">TABLE_GUID</span></span>|<span data-ttu-id="535fb-556">GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-556">Guid</span></span>|  
|<span data-ttu-id="535fb-557">설명</span><span class="sxs-lookup"><span data-stu-id="535fb-557">DESCRIPTION</span></span>|<span data-ttu-id="535fb-558">String</span><span class="sxs-lookup"><span data-stu-id="535fb-558">String</span></span>|  
|<span data-ttu-id="535fb-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="535fb-559">TABLE_PROPID</span></span>|<span data-ttu-id="535fb-560">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-560">Int64</span></span>|  
|<span data-ttu-id="535fb-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="535fb-561">DATE_CREATED</span></span>|<span data-ttu-id="535fb-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="535fb-562">DateTime</span></span>|  
|<span data-ttu-id="535fb-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="535fb-563">DATE_MODIFIED</span></span>|<span data-ttu-id="535fb-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="535fb-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="535fb-565">열</span><span class="sxs-lookup"><span data-stu-id="535fb-565">Columns</span></span>  
  
|<span data-ttu-id="535fb-566">ColumnName</span><span class="sxs-lookup"><span data-stu-id="535fb-566">ColumnName</span></span>|<span data-ttu-id="535fb-567">DataType</span><span class="sxs-lookup"><span data-stu-id="535fb-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="535fb-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-568">TABLE_CATALOG</span></span>|<span data-ttu-id="535fb-569">String</span><span class="sxs-lookup"><span data-stu-id="535fb-569">String</span></span>|  
|<span data-ttu-id="535fb-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="535fb-571">String</span><span class="sxs-lookup"><span data-stu-id="535fb-571">String</span></span>|  
|<span data-ttu-id="535fb-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-572">TABLE_NAME</span></span>|<span data-ttu-id="535fb-573">String</span><span class="sxs-lookup"><span data-stu-id="535fb-573">String</span></span>|  
|<span data-ttu-id="535fb-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-574">COLUMN_NAME</span></span>|<span data-ttu-id="535fb-575">String</span><span class="sxs-lookup"><span data-stu-id="535fb-575">String</span></span>|  
|<span data-ttu-id="535fb-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-576">COLUMN_GUID</span></span>|<span data-ttu-id="535fb-577">GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-577">Guid</span></span>|  
|<span data-ttu-id="535fb-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="535fb-578">COLUMN_PROPID</span></span>|<span data-ttu-id="535fb-579">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-579">Int64</span></span>|  
|<span data-ttu-id="535fb-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="535fb-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="535fb-581">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-581">Int64</span></span>|  
|<span data-ttu-id="535fb-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="535fb-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="535fb-583">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-583">Boolean</span></span>|  
|<span data-ttu-id="535fb-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="535fb-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="535fb-585">String</span><span class="sxs-lookup"><span data-stu-id="535fb-585">String</span></span>|  
|<span data-ttu-id="535fb-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="535fb-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="535fb-587">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-587">Int64</span></span>|  
|<span data-ttu-id="535fb-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="535fb-588">IS_NULLABLE</span></span>|<span data-ttu-id="535fb-589">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-589">Boolean</span></span>|  
|<span data-ttu-id="535fb-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="535fb-590">DATA_TYPE</span></span>|<span data-ttu-id="535fb-591">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-591">Int32</span></span>|  
|<span data-ttu-id="535fb-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-592">TYPE_GUID</span></span>|<span data-ttu-id="535fb-593">GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-593">Guid</span></span>|  
|<span data-ttu-id="535fb-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="535fb-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="535fb-595">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-595">Int64</span></span>|  
|<span data-ttu-id="535fb-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="535fb-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="535fb-597">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-597">Int64</span></span>|  
|<span data-ttu-id="535fb-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="535fb-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="535fb-599">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-599">Int32</span></span>|  
|<span data-ttu-id="535fb-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="535fb-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="535fb-601">Int16</span><span class="sxs-lookup"><span data-stu-id="535fb-601">Int16</span></span>|  
|<span data-ttu-id="535fb-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="535fb-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="535fb-603">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-603">Int64</span></span>|  
|<span data-ttu-id="535fb-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="535fb-605">String</span><span class="sxs-lookup"><span data-stu-id="535fb-605">String</span></span>|  
|<span data-ttu-id="535fb-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="535fb-607">String</span><span class="sxs-lookup"><span data-stu-id="535fb-607">String</span></span>|  
|<span data-ttu-id="535fb-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="535fb-609">String</span><span class="sxs-lookup"><span data-stu-id="535fb-609">String</span></span>|  
|<span data-ttu-id="535fb-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="535fb-611">String</span><span class="sxs-lookup"><span data-stu-id="535fb-611">String</span></span>|  
|<span data-ttu-id="535fb-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="535fb-613">String</span><span class="sxs-lookup"><span data-stu-id="535fb-613">String</span></span>|  
|<span data-ttu-id="535fb-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-614">COLLATION_NAME</span></span>|<span data-ttu-id="535fb-615">String</span><span class="sxs-lookup"><span data-stu-id="535fb-615">String</span></span>|  
|<span data-ttu-id="535fb-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="535fb-617">String</span><span class="sxs-lookup"><span data-stu-id="535fb-617">String</span></span>|  
|<span data-ttu-id="535fb-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="535fb-619">String</span><span class="sxs-lookup"><span data-stu-id="535fb-619">String</span></span>|  
|<span data-ttu-id="535fb-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-620">DOMAIN_NAME</span></span>|<span data-ttu-id="535fb-621">String</span><span class="sxs-lookup"><span data-stu-id="535fb-621">String</span></span>|  
|<span data-ttu-id="535fb-622">설명</span><span class="sxs-lookup"><span data-stu-id="535fb-622">DESCRIPTION</span></span>|<span data-ttu-id="535fb-623">String</span><span class="sxs-lookup"><span data-stu-id="535fb-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="535fb-624">프로시저</span><span class="sxs-lookup"><span data-stu-id="535fb-624">Procedures</span></span>  
  
|<span data-ttu-id="535fb-625">ColumnName</span><span class="sxs-lookup"><span data-stu-id="535fb-625">ColumnName</span></span>|<span data-ttu-id="535fb-626">DataType</span><span class="sxs-lookup"><span data-stu-id="535fb-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="535fb-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="535fb-628">String</span><span class="sxs-lookup"><span data-stu-id="535fb-628">String</span></span>|  
|<span data-ttu-id="535fb-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="535fb-630">String</span><span class="sxs-lookup"><span data-stu-id="535fb-630">String</span></span>|  
|<span data-ttu-id="535fb-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="535fb-632">String</span><span class="sxs-lookup"><span data-stu-id="535fb-632">String</span></span>|  
|<span data-ttu-id="535fb-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="535fb-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="535fb-634">Int16</span><span class="sxs-lookup"><span data-stu-id="535fb-634">Int16</span></span>|  
|<span data-ttu-id="535fb-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="535fb-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="535fb-636">String</span><span class="sxs-lookup"><span data-stu-id="535fb-636">String</span></span>|  
|<span data-ttu-id="535fb-637">설명</span><span class="sxs-lookup"><span data-stu-id="535fb-637">DESCRIPTION</span></span>|<span data-ttu-id="535fb-638">String</span><span class="sxs-lookup"><span data-stu-id="535fb-638">String</span></span>|  
|<span data-ttu-id="535fb-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="535fb-639">DATE_CREATED</span></span>|<span data-ttu-id="535fb-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="535fb-640">DateTime</span></span>|  
|<span data-ttu-id="535fb-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="535fb-641">DATE_MODIFIED</span></span>|<span data-ttu-id="535fb-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="535fb-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="535fb-643">보기</span><span class="sxs-lookup"><span data-stu-id="535fb-643">Views</span></span>  
  
|<span data-ttu-id="535fb-644">ColumnName</span><span class="sxs-lookup"><span data-stu-id="535fb-644">ColumnName</span></span>|<span data-ttu-id="535fb-645">DataType</span><span class="sxs-lookup"><span data-stu-id="535fb-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="535fb-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-646">TABLE_CATALOG</span></span>|<span data-ttu-id="535fb-647">String</span><span class="sxs-lookup"><span data-stu-id="535fb-647">String</span></span>|  
|<span data-ttu-id="535fb-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="535fb-649">String</span><span class="sxs-lookup"><span data-stu-id="535fb-649">String</span></span>|  
|<span data-ttu-id="535fb-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-650">TABLE_NAME</span></span>|<span data-ttu-id="535fb-651">String</span><span class="sxs-lookup"><span data-stu-id="535fb-651">String</span></span>|  
|<span data-ttu-id="535fb-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="535fb-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="535fb-653">String</span><span class="sxs-lookup"><span data-stu-id="535fb-653">String</span></span>|  
|<span data-ttu-id="535fb-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="535fb-654">CHECK_OPTION</span></span>|<span data-ttu-id="535fb-655">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-655">Boolean</span></span>|  
|<span data-ttu-id="535fb-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="535fb-656">IS_UPDATABLE</span></span>|<span data-ttu-id="535fb-657">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-657">Boolean</span></span>|  
|<span data-ttu-id="535fb-658">설명</span><span class="sxs-lookup"><span data-stu-id="535fb-658">DESCRIPTION</span></span>|<span data-ttu-id="535fb-659">String</span><span class="sxs-lookup"><span data-stu-id="535fb-659">String</span></span>|  
|<span data-ttu-id="535fb-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="535fb-660">DATE_CREATED</span></span>|<span data-ttu-id="535fb-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="535fb-661">DateTime</span></span>|  
|<span data-ttu-id="535fb-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="535fb-662">DATE_MODIFIED</span></span>|<span data-ttu-id="535fb-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="535fb-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="535fb-664">인덱스</span><span class="sxs-lookup"><span data-stu-id="535fb-664">Indexes</span></span>  
  
|<span data-ttu-id="535fb-665">ColumnName</span><span class="sxs-lookup"><span data-stu-id="535fb-665">ColumnName</span></span>|<span data-ttu-id="535fb-666">DataType</span><span class="sxs-lookup"><span data-stu-id="535fb-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="535fb-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-667">TABLE_CATALOG</span></span>|<span data-ttu-id="535fb-668">String</span><span class="sxs-lookup"><span data-stu-id="535fb-668">String</span></span>|  
|<span data-ttu-id="535fb-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="535fb-670">String</span><span class="sxs-lookup"><span data-stu-id="535fb-670">String</span></span>|  
|<span data-ttu-id="535fb-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-671">TABLE_NAME</span></span>|<span data-ttu-id="535fb-672">String</span><span class="sxs-lookup"><span data-stu-id="535fb-672">String</span></span>|  
|<span data-ttu-id="535fb-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="535fb-673">INDEX_CATALOG</span></span>|<span data-ttu-id="535fb-674">String</span><span class="sxs-lookup"><span data-stu-id="535fb-674">String</span></span>|  
|<span data-ttu-id="535fb-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="535fb-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="535fb-676">String</span><span class="sxs-lookup"><span data-stu-id="535fb-676">String</span></span>|  
|<span data-ttu-id="535fb-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-677">INDEX_NAME</span></span>|<span data-ttu-id="535fb-678">String</span><span class="sxs-lookup"><span data-stu-id="535fb-678">String</span></span>|  
|<span data-ttu-id="535fb-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="535fb-679">PRIMARY_KEY</span></span>|<span data-ttu-id="535fb-680">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-680">Boolean</span></span>|  
|<span data-ttu-id="535fb-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="535fb-681">UNIQUE</span></span>|<span data-ttu-id="535fb-682">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-682">Boolean</span></span>|  
|<span data-ttu-id="535fb-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="535fb-683">CLUSTERED</span></span>|<span data-ttu-id="535fb-684">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-684">Boolean</span></span>|  
|<span data-ttu-id="535fb-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="535fb-685">TYPE</span></span>|<span data-ttu-id="535fb-686">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-686">Int32</span></span>|  
|<span data-ttu-id="535fb-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="535fb-687">FILL_FACTOR</span></span>|<span data-ttu-id="535fb-688">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-688">Int32</span></span>|  
|<span data-ttu-id="535fb-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="535fb-689">INITIAL_SIZE</span></span>|<span data-ttu-id="535fb-690">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-690">Int32</span></span>|  
|<span data-ttu-id="535fb-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="535fb-691">NULLS</span></span>|<span data-ttu-id="535fb-692">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-692">Int32</span></span>|  
|<span data-ttu-id="535fb-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="535fb-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="535fb-694">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-694">Boolean</span></span>|  
|<span data-ttu-id="535fb-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="535fb-695">AUTO_UPDATE</span></span>|<span data-ttu-id="535fb-696">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-696">Boolean</span></span>|  
|<span data-ttu-id="535fb-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="535fb-697">NULL_COLLATION</span></span>|<span data-ttu-id="535fb-698">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-698">Int32</span></span>|  
|<span data-ttu-id="535fb-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="535fb-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="535fb-700">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-700">Int64</span></span>|  
|<span data-ttu-id="535fb-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="535fb-701">COLUMN_NAME</span></span>|<span data-ttu-id="535fb-702">String</span><span class="sxs-lookup"><span data-stu-id="535fb-702">String</span></span>|  
|<span data-ttu-id="535fb-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-703">COLUMN_GUID</span></span>|<span data-ttu-id="535fb-704">GUID</span><span class="sxs-lookup"><span data-stu-id="535fb-704">Guid</span></span>|  
|<span data-ttu-id="535fb-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="535fb-705">COLUMN_PROPID</span></span>|<span data-ttu-id="535fb-706">Int64</span><span class="sxs-lookup"><span data-stu-id="535fb-706">Int64</span></span>|  
|<span data-ttu-id="535fb-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="535fb-707">COLLATION</span></span>|<span data-ttu-id="535fb-708">Int16</span><span class="sxs-lookup"><span data-stu-id="535fb-708">Int16</span></span>|  
|<span data-ttu-id="535fb-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="535fb-709">CARDINALITY</span></span>|<span data-ttu-id="535fb-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="535fb-710">Decimal</span></span>|  
|<span data-ttu-id="535fb-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="535fb-711">PAGES</span></span>|<span data-ttu-id="535fb-712">Int32</span><span class="sxs-lookup"><span data-stu-id="535fb-712">Int32</span></span>|  
|<span data-ttu-id="535fb-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="535fb-713">FILTER_CONDITION</span></span>|<span data-ttu-id="535fb-714">String</span><span class="sxs-lookup"><span data-stu-id="535fb-714">String</span></span>|  
|<span data-ttu-id="535fb-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="535fb-715">INTEGRATED</span></span>|<span data-ttu-id="535fb-716">부울</span><span class="sxs-lookup"><span data-stu-id="535fb-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="535fb-717">참고 항목</span><span class="sxs-lookup"><span data-stu-id="535fb-717">See also</span></span>

- [<span data-ttu-id="535fb-718">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="535fb-718">ADO.NET Overview</span></span>](ado-net-overview.md)
