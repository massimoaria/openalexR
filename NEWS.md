# openalexR 2.0.1

# openalexR 2.0.0

# openalexR 2.0.0

# openalexR 2.0.0
* Breaking changes in column names in the output of `oa_fetch`:
  * Works:
    * `so` is now `source_display_name`
    * `so_id` is now `source_id`
    * `host_organization` now contains the id of the host organization
    * `host_organization_name` now contains the name of the host organization
    * `ab` is now `abstract`
    * `url` is now `landing_page_url`
    * `author` is now `authorships`
    * the nested columns under `authors` no longer have the `au` prefix
    * New columns: `fwci`, `referenced_works_count`, `keywords`
  * Authors:
    * `affiliation*` is removed
    * New columns: `last_known_institutions`, `2yr_mean_citedness`, `h_index`, `i10_index`
* Removed `concepts` as an entity
* Added `keywords` as an entity
* Added `get_coverage()` to track the oa2df-mapped columns of OpenAlex fields
  
* Deprecated `oa2bibliometrix()`. Use `bibliometrix::convert2df()` 
(from the **bibliometrix** R package) instead.

# openalexR 1.4.0
* "topics" are now a valid entity in oa_fetch
* The column "topics" replaces concepts in most entities' returned dataframes
* For Works, "topics" and "concepts" are now returned as separate columns

# openalexR 1.3.1
* solved bug in au_affiliation_raw in PR#241

# openalexR 1.3.0
* Breaking change: two arguments in `oa_snowball` are renamed:
`citing_filter` is now `citing_params`,
and `cited_by_filter` is now `cited_by_params`.
* Introduced `oa_generate`: A generator function to make request to OpenAlex API
and returns one record at a time.
* Fixed queries with `group_by`.
* Improved paging control: the user can now specify the `pages` they want in 
`oa_fetch` or `oa_request`.
* Improve `oa_snowball` performance.
* Allowed the use of `options$sample` with `search`.
* "venues"" is no longer a valid value for `entity`. Use "sources" instead.

# openalexR 1.2.2
* solved issue with CRAN test
* 

# openalexR 1.2.1
* many improvements in bibliometrix support
* solved issue with CRAN test

# openalexR 1.2.0
* many improvements in oa_snowball
* added new openalex entities
* solved CRAN issue about  packageVersion() 

# openalexR 1.1.0
* Basic paging is applied when using options$sample
* Bug fixes for rbind in oa2df

# openalexR 1.0.2.9
* Breaking change: Reorder of the first two arguments in `oa_fetch`: `entity` now comes before `idenfitifier`.
This should not affect your workflow too much unless you have been getting article information from OpenAlex IDs.
* new arguments to `oa_fetch`: `sample` and `seed` allows the user to download a random subset of the entities instead of the entire set.
* `oa_ngrams` gets you N-grams of works
* `abstract` now defaults to TRUE to avoid issues.
* New argument to oa_fetch: api_key
* Arguments sample, seed, sort, and select are now grouped into `options`.
* Bug fixes
* Improved documentation: group functions in Reference, details on search, etc.

# openalexR 1.0.1

* Improve `snowball` #9.
* Batch queries when a filter has more than 50 values #18.
* Bug fixes.
* Added a `NEWS.md` file to track changes to the package.

# openalexR 1.0.0
* Breaking change: now uses a more canonical way to filter #7.
* In `oa_fetch`, `abstract` now defaults to FALSE to save compute/query time/space. You will need to set `abstract = TRUE` to retrieve abstracts for the articles.
* Added website, hex.
* Added tests.
* Added R CMD CHECK as a GH Action
* Bug fixes.
* Added vignettes.

# openalexR 0.0.2
* Some bug fixes

# openalexR 0.0.1
* First CRAN release
