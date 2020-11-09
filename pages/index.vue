<template>
	<v-container>
		<v-row>
			<v-col>
				<v-container>
					<v-card>
						<v-row
							justify="center"
							class="my-6 pt-6">
							<v-avatar size="256">
								<v-img
									src="/rowleyj.dev/jesse-rowley.jpeg"
									max-height="350"
									max-width="350"
								></v-img>
							</v-avatar>							
						</v-row>
						<v-row
							justify="center"
							class="mx-12 my-4 px-10">
							<p>Hello! My name is <boldText text="Jesse Rowley"/>, and I am a Hamilton-based developer and entrepreneur. I am currently working
								on the Unified Communcations Team at BlackBerry as an intern where I focus on developing extensible full stack applications. For <boldText text="Summer 2021"/>, I am open and interested in new internship opportunities ranging from quantum computing, machine learning, project management, to full stack development.</p>
						</v-row>
						<v-divider></v-divider>
						<v-row
							justify="center"
						>
							<v-btn
								class="mx-1 my-4"
								icon
								large
								elevation="4"
								href="https://www.linkedin.com/in/jessewrowley/"
								target="_blank"
							>
								<v-icon>mdi-linkedin</v-icon>
							</v-btn>
							<v-btn
								class="mx-1 my-4"
								icon
								large
								elevation="4"
								target="_blank"
								href="https://github.com/rowleyj">
								<v-icon>mdi-github</v-icon></v-btn>
							
						</v-row>
						
					</v-card>
					
				</v-container>
			</v-col>
			<v-col>
				<v-container>
					<v-card>
						<v-row
							justify="center"
							class="my-6 pt-6">
							<h2>Previous Work</h2>
						</v-row>
						<v-divider></v-divider>
						<v-row
							justify="center"
							class="pa-6">
							<v-btn
								v-for="(work, index) in works"
								:key="index"
								outlined
								color="primary"
								class="ma-2"
								@click="workSelected = work;">{{work.title}}</v-btn>
						</v-row>
						<v-row
							v-if="workSelected">
							<v-col
								cols="12"
								xl="6">
								<v-row class="px-12">
									<p>
										<boldText text="Company:"/> {{workSelected.title}}
									</p>
								</v-row>
								<v-row class="px-12">
									<p>
										<boldText text="Role:" /> {{workSelected.job}}
									</p>
								</v-row>
								<v-row class="px-12">
									<p>
										<boldText text="Description:"/> {{workSelected.description}}
									</p>
								</v-row>
							</v-col>
							<v-col
								cols="12"
								xl="6">
								<v-row class="px-8">
									<v-list dense>
										<v-subheader>Technologies Used</v-subheader>
										<v-list-item
											v-for="(item, index) in workSelected.tech"
											:key="index">{{item}}</v-list-item>
									</v-list>
								</v-row>
							</v-col>
								
						</v-row>
					</v-card>
					
				</v-container>
			</v-col>
		</v-row>
	</v-container>
</template>

<script>
import boldText from '~/components/boldText'

export default {
	components: {
		boldText
	},
	data(){
		return{
			workSelected: {},
			works: [
				{
					title: 'RSearch',
					job: 'CEO and CTO',
					tech: ['NodeJS', 'NuxtJS', 'Google Cloud', 'IBM Cloud' , 'HubSpot', 'Docker'],
					description: 'I started RSearch to enable researchers to effectively market their studies requiring human participation to a wider audience. To do this I created a platform-as-a-service (PaaS) that allowed researchers to quickly post their studies, and market them on various social platforms while having a single point of contact. I onboarded several team members over my 2 years with RSearch, and spent several months in The Forge Startup Incubator.'
				},
				{
					title: 'Inflow Machine Learning',
					job: 'Senior Software Developer',
					tech: ['ReactJS','Redux', 'Leaflet', 'SocketIO'],
					description: 'I was brought on to help the team complete a short term contract, building out an user and admin dashboard for another company.'
				},
				{
					title: 'Get Learnt Podcast',
					job: 'Developer',
					tech: ['ReactJS', 'Adobe Premier'],
					description: 'I started the now defunct Get Learnt Podcast as a way to make science more digestible. During my time there I created a website for the podcast.'
				},
				{
					title: 'Mac AI Ventures',
					job: 'Head of Operations',
					tech: ['Statista', 'Draw.IO', 'Figma'],
					description: 'For the inaugural year of Mac AI Ventures, we began a pre-incubator program helping students develop their business ideas. I provided both technical and business insight for incubees as well as oversaw club events, and sponsorship.'
				},
				{
					title: 'BlackBerry',
					job: 'Unified Communcation Systems Student',
					tech: ['VueJS', 'Java', 'Tomcat', 'Bash', 'NodeJS'],
					description: 'At BlackBerry, I helped with larger projects such as the telephony consolidation of Cylance as well as smaller projects like developing front end applications, and new automation.'
				}
			]
		}
	},
	mounted(){
		this.workSelected = this.works[0]
	}
}
</script>