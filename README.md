import Image from "next/image"
import { ThumbsUp, ThumbsDown, Share2, Download, MoreHorizontal, Bell } from "lucide-react"

import { Button } from "@/components/ui/button"
import { Separator } from "@/components/ui/separator"

export default function YouTubePage() {
  return (
    <div className="mx-auto max-w-7xl p-4">
      <div className="grid grid-cols-1 gap-6 lg:grid-cols-3">
        <div className="lg:col-span-2">
          {/* Video Player */}
          <div className="aspect-video w-full overflow-hidden rounded-xl bg-black">
            <video className="h-full w-full" controls poster="/placeholder.svg?height=720&width=1280">
              <source src="#" type="video/mp4" />
              Your browser does not support the video tag.
            </video>
          </div>

          {/* Video Info */}
          <div className="mt-4">
            <h1 className="text-xl font-semibold">How to Build a Modern Website with Next.js and Tailwind CSS</h1>

            <div className="mt-4 flex flex-col justify-between gap-4 sm:flex-row sm:items-center">
              <div className="flex items-center gap-4">
                <Image
                  src="/placeholder.svg?height=48&width=48"
                  width={48}
                  height={48}
                  alt="Channel avatar"
                  className="rounded-full"
                />
                <div>
                  <h2 className="font-medium">Code Channel</h2>
                  <p className="text-sm text-muted-foreground">1.2M subscribers</p>
                </div>
                <Button variant="secondary" size="sm" className="ml-2 rounded-full">
                  <Bell className="mr-1 h-4 w-4" />
                  Subscribed
                </Button>
              </div>

              <div className="flex flex-wrap gap-2">
                <div className="flex overflow-hidden rounded-full bg-muted">
                  <Button variant="ghost" size="sm" className="rounded-l-full rounded-r-none border-r">
                    <ThumbsUp className="mr-1 h-4 w-4" />
                    24K
                  </Button>
                  <Button variant="ghost" size="sm" className="rounded-l-none rounded-r-full">
                    <ThumbsDown className="h-4 w-4" />
                  </Button>
                </div>

                <Button variant="ghost" size="sm" className="rounded-full">
                  <Share2 className="mr-1 h-4 w-4" />
                  Share
                </Button>

                <Button variant="ghost" size="sm" className="rounded-full">
                  <Download className="mr-1 h-4 w-4" />
                  Download
                </Button>

                <Button variant="ghost" size="sm" className="rounded-full px-2">
                  <MoreHorizontal className="h-4 w-4" />
                </Button>
              </div>
            </div>

            <div className="mt-4 rounded-xl bg-muted p-4">
              <div className="flex items-center gap-2 text-sm">
                <span className="font-medium">125K views</span>
                <span>•</span>
                <span>2 weeks ago</span>
              </div>
              <p className="mt-2 text-sm">
                In this comprehensive tutorial, we'll walk through building a modern, responsive website using Next.js
                and Tailwind CSS. Learn how to set up your project, create reusable components, and deploy your site to
                production.
              </p>
            </div>
          </div>
        </div>

        {/* Recommended Videos */}
        <div className="space-y-4">
          <h3 className="font-medium">Recommended videos</h3>

          {Array.from({ length: 5 }).map((_, i) => (
            <div key={i} className="flex gap-2">
              <div className="aspect-video w-40 flex-shrink-0 overflow-hidden rounded-lg bg-muted">
                <Image
                  src={`/placeholder.svg?height=90&width=160&text=Video ${i + 1}`}
                  width={160}
                  height={90}
                  alt={`Recommended video ${i + 1}`}
                  className="h-full w-full object-cover"
                />
              </div>
              <div className="flex-1">
                <h4 className="line-clamp-2 text-sm font-medium">
                  Building a Dashboard UI with React and Tailwind CSS
                </h4>
                <p className="mt-1 text-xs text-muted-foreground">Code Channel</p>
                <p className="text-xs text-muted-foreground">87K views • 3 days ago</p>
              </div>
            </div>
          ))}

          <Separator />

          {Array.from({ length: 3 }).map((_, i) => (
            <div key={i + 5} className="flex gap-2">
              <div className="aspect-video w-40 flex-shrink-0 overflow-hidden rounded-lg bg-muted">
                <Image
                  src={`/placeholder.svg?height=90&width=160&text=Video ${i + 6}`}
                  width={160}
                  height={90}
                  alt={`Recommended video ${i + 6}`}
                  className="h-full w-full object-cover"
                />
              </div>
              <div className="flex-1">
                <h4 className="line-clamp-2 text-sm font-medium">Advanced CSS Techniques for Modern Web Design</h4>
                <p className="mt-1 text-xs text-muted-foreground">Design Masters</p>
                <p className="text-xs text-muted-foreground">45K views • 1 week ago</p>
              </div>
            </div>
          ))}
        </div>
      </div>
    </div>
  )
}
