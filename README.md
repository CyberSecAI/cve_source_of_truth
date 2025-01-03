# cve_source_of_truth

This collates CVE info from several sources into one source.

### Problem statement

The most popular sets of truth for CVE data, cvelistV5 and NVD, do not properly allign all the time.
The goal of this repository is to keep an updated dataset of cvelistV5 enriched with NVD data.
Additionally, we want to create simple GraphQL API were users can request data in whatever format fits them.

An example of these inconsistencies is with `CVE-2021-46022`

Specified in cvelistV5:

```json
        "cna": {
            "providerMetadata": {
                "orgId": "8254265b-2729-46b6-b9e3-3dfca2d5bfca",
                "shortName": "mitre",
                "dateUpdated": "2023-11-13T22:41:58.698447"
            },
            "descriptions": [
                {
                    "lang": "en",
                    "value": "An Use-After-Free vulnerability in rec_mset_elem_destroy() at rec-mset.c of GNU Recutils v1.8.90 can lead to a segmentation fault or application crash."
                }
            ],
            "affected": [
                {
                    "vendor": "n/a",
                    "product": "n/a",
                    "versions": [
                        {
                            "version": "n/a",
                            "status": "affected"
                        }
                    ]
                }
            ],
            "references": [
                {
                    "url": "https://lists.gnu.org/archive/html/bug-recutils/2021-12/msg00007.html"
                },
                {
                    "name": "FEDORA-2022-4e6bd7ca62",
                    "tags": [
                        "vendor-advisory"
                    ],
                    "url": "https://lists.fedoraproject.org/archives/list/package-announce%40lists.fedoraproject.org/message/VRSXSN2XF6PX74WDYVV26TQMYIFAEQ3T/"
                },
                {
                    "name": "FEDORA-2022-17787e290f",
                    "tags": [
                        "vendor-advisory"
                    ],
                    "url": "https://lists.fedoraproject.org/archives/list/package-announce%40lists.fedoraproject.org/message/TDVOFC3HTBG7DF2PZTEXRMG4CV2F55UF/"
                },
                {
                    "url": "https://github.com/gnu-mirror-unofficial/recutils/commit/34b75ed7ad492c8e38b669ebafe0176f1f9992d2"
                },
                {
                    "url": "https://nvd.nist.gov/vuln/detail/CVE-2021-46022"
                }
            ],
            "problemTypes": [
                {
                    "descriptions": [
                        {
                            "type": "text",
                            "lang": "en",
                            "description": "n/a"
                        }
                    ]
                }
            ]
        },
```

Specified in NVD:
